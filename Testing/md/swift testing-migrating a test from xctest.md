

- Swift Testing
-  Migrating a test from XCTest 

Article

# Migrating a test from XCTest

Migrate an existing test method or test class written using XCTest.

## Overview

The testing library provides much of the same functionality of XCTest, but uses its own syntax to declare test functions and types. Here, you’ll learn how to convert XCTest-based content to use the testing library instead.

### Import the testing library

XCTest and the testing library are available from different modules. Instead of importing the XCTest module, import the Testing module:

```
// Before
import XCTest
```

```
// After
import Testing
```

A single source file can contain tests written with XCTest as well as other tests written with the testing library. Import both XCTest and Testing if a source file contains mixed test content.

### Convert test classes

XCTest groups related sets of test methods in test classes: classes that inherit from the XCTestCase class provided by the XCTest framework. The testing library doesn’t require that test functions be instance members of types. Instead, they can be *free* or *global* functions, or can be `static` or `class` members of a type.

If you want to group your test functions together, you can do so by placing them in a Swift type. The testing library refers to such a type as a *suite*. These types do *not* need to be classes, and they don’t inherit from `XCTestCase`.

To convert a subclass of `XCTestCase` to a suite, remove the `XCTestCase` conformance. It’s also generally recommended that a Swift structure or actor be used instead of a class because it allows the Swift compiler to better-enforce concurrency safety:

```
// Before
class FoodTruckTests: XCTestCase {
  ...
}
```

```
// After
struct FoodTruckTests {
  ...
}
```

For more information about suites and how to declare and customize them, see Organizing test functions with suite types.

### Convert setup and teardown functions

In XCTest, code can be scheduled to run before and after a test using the setUp() and tearDown() family of functions. When writing tests using the testing library, implement `init()` and/or `deinit` instead:

```
// Before
class FoodTruckTests: XCTestCase {
  var batteryLevel: NSNumber!
  override func setUp() async throws {
    batteryLevel = 100
  }
  ...
}
```

```
// After
struct FoodTruckTests {
  var batteryLevel: NSNumber
  init() async throws {
    batteryLevel = 100
  }
  ...
}
```

The use of `async` and `throws` is optional. If teardown is needed, declare your test suite as a class or as an actor rather than as a structure and implement `deinit`:

```
// Before
class FoodTruckTests: XCTestCase {
  var batteryLevel: NSNumber!
  override func setUp() async throws {
    batteryLevel = 100
  }
  override func tearDown() {
    batteryLevel = 0 // drain the battery
  }
  ...
}
```

```
// After
final class FoodTruckTests {
  var batteryLevel: NSNumber
  init() async throws {
    batteryLevel = 100
  }
  deinit {
    batteryLevel = 0 // drain the battery
  }
  ...
}
```

### Convert test methods

The testing library represents individual tests as functions, similar to how they are represented in XCTest. However, the syntax for declaring a test function is different. In XCTest, a test method must be a member of a test class and its name must start with `test`. The testing library doesn’t require a test function to have any particular name. Instead, it identifies a test function by the presence of the `@Test` attribute:

```
// Before
class FoodTruckTests: XCTestCase {
  func testEngineWorks() { ... }
  ...
}
```

```
// After
struct FoodTruckTests {
  @Test func engineWorks() { ... }
  ...
}
```

As with XCTest, the testing library allows test functions to be marked `async`, `throws`, or `async`-`throws`, and to be isolated to a global actor (for example, by using the `@MainActor` attribute.)

Note

XCTest runs synchronous test methods on the main actor by default, while the testing library runs all test functions on an arbitrary task. If a test function must run on the main thread, isolate it to the main actor with `@MainActor`, or run the thread-sensitive code inside a call to MainActor.run(resultType:body:).

For more information about test functions and how to declare and customize them, see Defining test functions.

### Check for expected values and outcomes

XCTest uses a family of approximately 40 functions to assert test requirements. These functions are collectively referred to as XCTAssert(). The testing library has two replacements, expect(_:_:sourceLocation:) and require(_:_:sourceLocation:). They both behave similarly to `XCTAssert()` except that require(_:_:sourceLocation:) throws an error if its condition isn’t met:

```
// Before
func testEngineWorks() throws {
  let engine = FoodTruck.shared.engine
  XCTAssertNotNil(engine.parts.first)
  XCTAssertGreaterThan(engine.batteryLevel, 0)
  try engine.start()
  XCTAssertTrue(engine.isRunning)
}
```

```
// After
@Test func engineWorks() throws {
  let engine = FoodTruck.shared.engine
  try #require(engine.parts.first != nil)
  #expect(engine.batteryLevel > 0)
  try engine.start()
  #expect(engine.isRunning)
}
```

### Check for optional values

XCTest also has a function, XCTUnwrap(), that tests if an optional value is `nil` and throws an error if it is. When using the testing library, you can use require(_:_:sourceLocation:) with optional expressions to unwrap them:

```
// Before
func testEngineWorks() throws {
  let engine = FoodTruck.shared.engine
  let part = try XCTUnwrap(engine.parts.first)
  ...
}
```

```
// After
@Test func engineWorks() throws {
  let engine = FoodTruck.shared.engine
  let part = try #require(engine.parts.first)
  ...
}
```

### Record issues

Finally, XCTest has a function, XCTFail(), that causes a test to fail immediately and unconditionally. This function is useful when the syntax of the language prevents the use of an `XCTAssert()` function. To record an unconditional issue using the testing library, use the record(_:sourceLocation:) function:

```
// Before
func testEngineWorks() {
  let engine = FoodTruck.shared.engine
  guard case .electric = engine else {
    XCTFail("Engine is not electric")
    return
  }
  ...
}
```

```
// After
@Test func engineWorks() {
  let engine = FoodTruck.shared.engine
  guard case .electric = engine else {
    Issue.record("Engine is not electric")
    return
  }
  ...
}
```

The following table includes a list of the various `XCTAssert()` functions and their equivalents in the testing library:

| XCTest | Swift Testing |
|----|----|
| `XCTAssert(x)`, `XCTAssertTrue(x)` | `#expect(x)` |
| `XCTAssertFalse(x)` | `#expect(!x)` |
| `XCTAssertNil(x)` | `#expect(x == nil)` |
| `XCTAssertNotNil(x)` | `#expect(x != nil)` |
| `XCTAssertEqual(x, y)` | `#expect(x == y)` |
| `XCTAssertNotEqual(x, y)` | `#expect(x != y)` |
| `XCTAssertIdentical(x, y)` | `#expect(x === y)` |
| `XCTAssertNotIdentical(x, y)` | `#expect(x !== y)` |
| `XCTAssertGreaterThan(x, y)` | `#expect(x > y)` |
| `XCTAssertGreaterThanOrEqual(x, y)` | `#expect(x >= y)` |
| `XCTAssertLessThanOrEqual(x, y)` | `#expect(x 

The testing library doesn’t provide an equivalent of XCTAssertEqual(_:_:accuracy:_:file:line:). To compare two numeric values within a specified accuracy, use `isApproximatelyEqual()` from swift-numerics.

### Continue or halt after test failures

An instance of an `XCTestCase` subclass can set its continueAfterFailure property to `false` to cause a test to stop running after a failure occurs. XCTest stops an affected test by throwing an Objective-C exception at the time the failure occurs.

Note

`continueAfterFailure` isn’t fully supported when using the swift-corelibs-xctest library on non-Apple platforms.

The behavior of an exception thrown through a Swift stack frame is undefined. If an exception is thrown through an `async` Swift function, it typically causes the process to terminate abnormally, preventing other tests from running.

The testing library doesn’t use exceptions to stop test functions. Instead, use the require(_:_:sourceLocation:) macro, which throws a Swift error on failure:

```
// Before
func testTruck() async {
  continueAfterFailure = false
  XCTAssertTrue(FoodTruck.shared.isLicensed)
  ...
}
```

```
// After
@Test func truck() throws {
  try #require(FoodTruck.shared.isLicensed)
  ...
}
```

When using either `continueAfterFailure` or require(_:_:sourceLocation:), other tests will continue to run after the failed test method or test function.

### Validate asynchronous behaviors

XCTest has a class, XCTestExpectation, that represents some asynchronous condition. You create an instance of this class (or a subclass like XCTKeyPathExpectation) using an initializer or a convenience method on `XCTestCase`. When the condition represented by an expectation occurs, the developer *fulfills* the expectation. Concurrently, the developer *waits for* the expectation to be fulfilled using an instance of XCTWaiter or using a convenience method on `XCTestCase`.

Wherever possible, prefer to use Swift concurrency to validate asynchronous conditions. For example, if it’s necessary to determine the result of an asynchronous Swift function, it can be awaited with `await`. For a function that takes a completion handler but which doesn’t use `await`, a Swift continuation can be used to convert the call into an `async`-compatible one.

Some tests, especially those that test asynchronously-delivered events, cannot be readily converted to use Swift concurrency. The testing library offers functionality called *confirmations* which can be used to implement these tests. Instances of Confirmation are created and used within the scope of the functions confirmation(_:expectedCount:isolation:sourceLocation:_:) and confirmation(_:expectedCount:isolation:sourceLocation:_:).

Confirmations function similarly to the expectations API of XCTest, however, they don’t block or suspend the caller while waiting for a condition to be fulfilled. Instead, the requirement is expected to be *confirmed* (the equivalent of *fulfilling* an expectation) before `confirmation()` returns, and records an issue otherwise:

```
// Before
func testTruckEvents() async {
  let soldFood = expectation(description: "…")
  FoodTruck.shared.eventHandler = { event in
    if case .soldFood = event {
      soldFood.fulfill()
    }
  }
  await Customer().buy(.soup)
  await fulfillment(of: [soldFood])
  ...
}
```

```
// After
@Test func truckEvents() async {
  await confirmation("…") { soldFood in
    FoodTruck.shared.eventHandler = { event in
      if case .soldFood = event {
        soldFood()
      }
    }
    await Customer().buy(.soup)
  }
  ...
}
```

By default, `XCTestExpectation` expects to be fulfilled exactly once, and will record an issue in the current test if it is not fulfilled or if it is fulfilled more than once. `Confirmation` behaves the same way and expects to be confirmed exactly once by default. You can configure the number of times an expectation should be fulfilled by setting its expectedFulfillmentCount property, and you can pass a value for the `expectedCount` argument of confirmation(_:expectedCount:isolation:sourceLocation:_:) for the same purpose.

`XCTestExpectation` has a property, assertForOverFulfill, which when set to `false` allows an expectation to be fulfilled more times than expected without causing a test failure. When using a confirmation, you can pass a range to confirmation(_:expectedCount:isolation:sourceLocation:_:) as its expected count to indicate that it must be confirmed *at least* some number of times:

```
// Before
func testRegularCustomerOrders() async {
  let soldFood = expectation(description: "…")
  soldFood.expectedFulfillmentCount = 10
  soldFood.assertForOverFulfill = false
  FoodTruck.shared.eventHandler = { event in
    if case .soldFood = event {
      soldFood.fulfill()
    }
  }
  for customer in regularCustomers() {
    await customer.buy(customer.regularOrder)
  }
  await fulfillment(of: [soldFood])
  ...
}
```

```
// After
@Test func regularCustomerOrders() async {
  await confirmation(
    "…",
    expectedCount: 10...
  ) { soldFood in
    FoodTruck.shared.eventHandler = { event in
      if case .soldFood = event {
        soldFood()
      }
    }
    for customer in regularCustomers() {
      await customer.buy(customer.regularOrder)
    }
  }
  ...
}
```

Any range expression with a lower bound (that is, whose type conforms to both RangeExpression&lt;Int> and Sequence&lt;Int>) can be used with confirmation(_:expectedCount:isolation:sourceLocation:_:). You must specify a lower bound for the number of confirmations because, without one, the testing library cannot tell if an issue should be recorded when there have been zero confirmations.

### Control whether a test runs

When using XCTest, the XCTSkip error type can be thrown to bypass the remainder of a test function. As well, the XCTSkipIf() and XCTSkipUnless() functions can be used to conditionalize the same action. The testing library allows developers to skip a test function or an entire test suite before it starts running using the ConditionTrait trait type. Annotate a test suite or test function with an instance of this trait type to control whether it runs:

```
// Before
class FoodTruckTests: XCTestCase {
  func testArepasAreTasty() throws {
    try XCTSkipIf(CashRegister.isEmpty)
    try XCTSkipUnless(FoodTruck.sells(.arepas))
    ...
  }
  ...
}
```

```
// After
@Suite(.disabled(if: CashRegister.isEmpty))
struct FoodTruckTests {
  @Test(.enabled(if: FoodTruck.sells(.arepas)))
  func arepasAreTasty() {
    ...
  }
  ...
}
```

### Annotate known issues

A test may have a known issue that sometimes or always prevents it from passing. When written using XCTest, such tests can call XCTExpectFailure(_:options:failingBlock:) to tell XCTest and its infrastructure that the issue shouldn’t cause the test to fail. The testing library has an equivalent function with synchronous and asynchronous variants:

- withKnownIssue(_:isIntermittent:sourceLocation:_:)

- withKnownIssue(_:isIntermittent:isolation:sourceLocation:_:)

This function can be used to annotate a section of a test as having a known issue:

```
// Before
func testGrillWorks() async {
  XCTExpectFailure("Grill is out of fuel") {
    try FoodTruck.shared.grill.start()
  }
  ...
}
```

```
// After
@Test func grillWorks() async {
  withKnownIssue("Grill is out of fuel") {
    try FoodTruck.shared.grill.start()
  }
  ...
}
```

Note

The XCTest function XCTExpectFailure(_:options:), which doesn’t take a closure and which affects the remainder of the test, doesn’t have a direct equivalent in the testing library. To mark an entire test as having a known issue, wrap its body in a call to `withKnownIssue()`.

If a test may fail intermittently, the call to `XCTExpectFailure(_:options:failingBlock:)` can be marked *non-strict*. When using the testing library, specify that the known issue is *intermittent* instead:

```
// Before
func testGrillWorks() async {
  XCTExpectFailure(
    "Grill may need fuel",
    options: .nonStrict()
  ) {
    try FoodTruck.shared.grill.start()
  }
  ...
}
```

```
// After
@Test func grillWorks() async {
  withKnownIssue(
    "Grill may need fuel", 
    isIntermittent: true
  ) {
    try FoodTruck.shared.grill.start()
  }
  ...
}
```

Additional options can be specified when calling `XCTExpectFailure()`:

- isEnabled can be set to `false` to skip known-issue matching (for instance, if a particular issue only occurs under certain conditions)

- issueMatcher can be set to a closure to allow marking only certain issues as known and to allow other issues to be recorded as test failures

The testing library includes overloads of `withKnownIssue()` that take additional arguments with similar behavior:

- withKnownIssue(_:isIntermittent:sourceLocation:_:when:matching:)

- withKnownIssue(_:isIntermittent:isolation:sourceLocation:_:when:matching:)

To conditionally enable known-issue matching or to match only certain kinds of issues:

```
// Before
func testGrillWorks() async {
  let options = XCTExpectedFailure.Options()
  options.isEnabled = FoodTruck.shared.hasGrill
  options.issueMatcher = { issue in
    issue.type == thrownError
  }
  XCTExpectFailure(
    "Grill is out of fuel",
    options: options
  ) {
    try FoodTruck.shared.grill.start()
  }
  ...
}
```

```
// After
@Test func grillWorks() async {
  withKnownIssue("Grill is out of fuel") {
    try FoodTruck.shared.grill.start()
  } when: {
    FoodTruck.shared.hasGrill
  } matching: { issue in
    issue.error != nil 
  }
  ...
}
```

## See Also

### Related Documentation

Defining test functions

Define a test function to validate that code is working correctly.

Organizing test functions with suite types

Organize tests into test suites.

Expectations and confirmations

Check for expected values, outcomes, and asynchronous events in tests.

Known issues

Highlight known issues when running tests.

### Essentials

Defining test functions

Define a test function to validate that code is working correctly.

Organizing test functions with suite types

Organize tests into test suites.

macro Test(String?, any TestTrait...)

Declare a test.

struct Test

A type representing a test or suite.

macro Suite(String?, any SuiteTrait...)

Declare a test suite.

