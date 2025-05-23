

- Exception Handling
- NSExceptionHandler
-  Exception Global String Constants 

API Collection

# Exception Global String Constants

Two of the following global string constants identify exceptions generated by the framework for Objective-C runtime errors and system exceptions such as invalid memory accesses. The other constant is used as a key to access the stack trace in the userInfo dictionary of an NSException object, when requested.

## Topics

### Constants

let NSUncaughtSystemExceptionException: String

Identifies an uncaught system exception.

let NSUncaughtRuntimeErrorException: String

Identifies an Objective-C runtime error.

let NSStackTraceKey: String

The key for fetching the stack trace (an NSString object) in the userInfo dictionary of the NSException object passed into one of the delegate methods described in NSExceptionHandlerDelegate.

## See Also

### Constants

Logging and Handling Constants

Use one or more of the following constants in the parameter of setExceptionHandlingMask(_:) to specify the types of exceptions that the exception handler should monitor and whether it should handle or log them.

System Hang Constants

Use one or more of the following constants in the parameter of setExceptionHangingMask(_:) to specify the types of exceptions that cause the exception to halt execution so a debugger can be attached.

