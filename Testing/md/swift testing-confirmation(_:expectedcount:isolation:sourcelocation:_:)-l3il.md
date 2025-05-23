

- Swift Testing
-  confirmation(\_:expectedCount:isolation:sourceLocation:\_:) 

Function

# confirmation(\_:expectedCount:isolation:sourceLocation:\_:)

Confirm that some event occurs during the invocation of a function.

Swift 6.1+Xcode 16.3+

``` source
func confirmation(
    _ comment: Comment? = nil,
    expectedCount: some RangeExpression & Sendable & Sequence,
    isolation: isolated (any Actor)? = #isolation,
    sourceLocation: SourceLocation = #_sourceLocation,
    _ body: (Confirmation) async throws -> sending R
) async rethrows -> R
```

## Parameters 

`comment`  

An optional comment to apply to any issues generated by this function.

`expectedCount`  

A range of integers indicating the number of times the expected event should occur when `body` is invoked.

`isolation`  

The actor to which `body` is isolated, if any.

`sourceLocation`  

The source location to which any recorded issues should be attributed.

`body`  

The function to invoke.

## Return Value

Whatever is returned by `body`.

## Mentioned in 

Migrating a test from XCTest

Testing asynchronous code

## Discussion

Throws

Whatever is thrown by `body`.

Use confirmations to check that an event occurs while a test is running in complex scenarios where `#expect()` and `#require()` are insufficient. For example, a confirmation may be useful when an expected event occurs:

- In a context that cannot be awaited by the calling function such as an event handler or delegate callback;

- More than once, or never; or

- As a callback that is invoked as part of a larger operation.

To use a confirmation, pass a closure containing the work to be performed. The testing library will then pass an instance of Confirmation to the closure. Every time the event in question occurs, the closure should call the confirmation:

```
let minBuns = 5
let maxBuns = 10
await confirmation(
  "Baked between \(minBuns) and \(maxBuns) buns",
  expectedCount: minBuns ... maxBuns
) { bunBaked in
  foodTruck.eventHandler = { event in
    if event == .baked(.cinnamonBun) {
      bunBaked()
    }
  }
  await foodTruck.bakeTray(of: .cinnamonBun)
}
```

When the closure returns, the testing library checks if the confirmation’s preconditions have been met, and records an issue if they have not.

If an exact count is expected, use confirmation(_:expectedCount:isolation:sourceLocation:_:) instead.

## See Also

### Confirming that asynchronous events occur

Testing asynchronous code

Validate whether your code causes expected events to happen.

func confirmation&lt;R>(Comment?, expectedCount: Int, isolation: isolated (any Actor)?, sourceLocation: SourceLocation, (Confirmation) async throws -> sending R) async rethrows -> R

Confirm that some event occurs during the invocation of a function.

struct Confirmation

A type that can be used to confirm that an event occurs zero or more times.

