

- App Store Connect API
- CiTestResult
-  CiTestResult.Attributes 

Object

# CiTestResult.Attributes

The attributes that describe a Test Results resource.

App Store Connect API 1.5+

``` source
object CiTestResult.Attributes
```

## Properties

`className`

`string`

The name of the class that contained the tests Xcode Cloud performed.

`destinationTestResults`

`[`CiTestResult.Attributes.DestinationTestResults`]`

Information about the test results for a specific test destination.

`fileSource`

FileLocation

Information about a test file.

`message`

`string`

A message generated by a test.

`name`

`string`

The name of the test result; for example, ExampleName.

`status`

CiTestStatus

Test status information; for example, whether the test succeeded or failed.

## Topics

### Objects and Types

object CiTestResult.Attributes.DestinationTestResults

The results of a test action Xcode Cloud performed using a specific test destination.

type CiTestStatus

A string that represents test status information.

