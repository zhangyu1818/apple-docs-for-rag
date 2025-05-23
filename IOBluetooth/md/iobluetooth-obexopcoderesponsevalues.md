

- IOBluetooth
-  OBEXOpCodeResponseValues 

Structure

# OBEXOpCodeResponseValues

Response opCode values.

macOS

``` source
struct OBEXOpCodeResponseValues
```

## Topics

### Constants

var kOBEXResponseCodeAccepted: OBEXOpCodeResponseValues

var kOBEXResponseCodeAcceptedWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeBadGateway: OBEXOpCodeResponseValues

var kOBEXResponseCodeBadGatewayWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeBadRequest: OBEXOpCodeResponseValues

var kOBEXResponseCodeBadRequestWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeConflict: OBEXOpCodeResponseValues

var kOBEXResponseCodeConflictWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeContinue: OBEXOpCodeResponseValues

var kOBEXResponseCodeContinueWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeCreated: OBEXOpCodeResponseValues

var kOBEXResponseCodeCreatedWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeDatabaseFull: OBEXOpCodeResponseValues

var kOBEXResponseCodeDatabaseFullWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeDatabaseLocked: OBEXOpCodeResponseValues

var kOBEXResponseCodeDatabaseLockedWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeForbidden: OBEXOpCodeResponseValues

var kOBEXResponseCodeForbiddenWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeGatewayTimeout: OBEXOpCodeResponseValues

var kOBEXResponseCodeGatewayTimeoutWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeGone: OBEXOpCodeResponseValues

var kOBEXResponseCodeGoneWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeHTTPVersionNotSupported: OBEXOpCodeResponseValues

var kOBEXResponseCodeHTTPVersionNotSupportedWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeInternalServerError: OBEXOpCodeResponseValues

var kOBEXResponseCodeInternalServerErrorWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeLengthRequired: OBEXOpCodeResponseValues

var kOBEXResponseCodeLengthRequiredFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeMethodNotAllowed: OBEXOpCodeResponseValues

var kOBEXResponseCodeMethodNotAllowedWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeMovedPermanently: OBEXOpCodeResponseValues

var kOBEXResponseCodeMovedPermanentlyWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeMovedTemporarily: OBEXOpCodeResponseValues

var kOBEXResponseCodeMovedTemporarilyWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeMultipleChoices: OBEXOpCodeResponseValues

var kOBEXResponseCodeMultipleChoicesWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeNoContent: OBEXOpCodeResponseValues

var kOBEXResponseCodeNoContentWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeNonAuthoritativeInfo: OBEXOpCodeResponseValues

var kOBEXResponseCodeNonAuthoritativeInfoWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeNotAcceptable: OBEXOpCodeResponseValues

var kOBEXResponseCodeNotAcceptableWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeNotFound: OBEXOpCodeResponseValues

var kOBEXResponseCodeNotFoundWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeNotImplemented: OBEXOpCodeResponseValues

var kOBEXResponseCodeNotImplementedWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeNotModified: OBEXOpCodeResponseValues

var kOBEXResponseCodeNotModifiedWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodePartialContent: OBEXOpCodeResponseValues

var kOBEXResponseCodePartialContentWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodePaymentRequired: OBEXOpCodeResponseValues

var kOBEXResponseCodePaymentRequiredWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodePreconditionFailed: OBEXOpCodeResponseValues

var kOBEXResponseCodePreconditionFailedWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeProxyAuthenticationRequired: OBEXOpCodeResponseValues

var kOBEXResponseCodeProxyAuthenticationRequiredWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeRequestTimeOut: OBEXOpCodeResponseValues

var kOBEXResponseCodeRequestTimeOutWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeRequestURLTooLarge: OBEXOpCodeResponseValues

var kOBEXResponseCodeRequestURLTooLargeWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeRequestedEntityTooLarge: OBEXOpCodeResponseValues

var kOBEXResponseCodeRequestedEntityTooLargeWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeReservedRangeEnd: OBEXOpCodeResponseValues

var kOBEXResponseCodeReservedRangeStart: OBEXOpCodeResponseValues

var kOBEXResponseCodeResetContent: OBEXOpCodeResponseValues

var kOBEXResponseCodeResetContentWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeSeeOther: OBEXOpCodeResponseValues

var kOBEXResponseCodeSeeOtherWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeServiceUnavailable: OBEXOpCodeResponseValues

var kOBEXResponseCodeServiceUnavailableWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeSuccess: OBEXOpCodeResponseValues

var kOBEXResponseCodeSuccessWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeUnauthorized: OBEXOpCodeResponseValues

var kOBEXResponseCodeUnauthorizedWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeUnsupportedMediaType: OBEXOpCodeResponseValues

var kOBEXResponseCodeUnsupportedMediaTypeWithFinalBit: OBEXOpCodeResponseValues

var kOBEXResponseCodeUseProxy: OBEXOpCodeResponseValues

var kOBEXResponseCodeUseProxyWithFinalBit: OBEXOpCodeResponseValues

### Initializers

init(UInt32)

init(rawValue: UInt32)

### Instance Properties

var rawValue: UInt32

## Relationships

### Conforms To

- BitwiseCopyable
- Equatable
- Hashable
- RawRepresentable
- Sendable

## See Also

### Data Types

typealias BluetoothAFHMode

typealias BluetoothAirMode

typealias BluetoothAllowRoleSwitch

typealias BluetoothAuthenticationRequirements

struct BluetoothAuthenticationRequirementsValues

typealias BluetoothClassOfDevice

typealias BluetoothClockOffset

struct BluetoothCompanyIdentifers

typealias BluetoothConnectionHandle

typealias BluetoothDeviceClassMajor

typealias BluetoothDeviceClassMinor

typealias BluetoothDeviceName

typealias BluetoothEncryptionEnable

struct BluetoothFeatureBits

typealias BluetoothHCIACLDataByteCount

