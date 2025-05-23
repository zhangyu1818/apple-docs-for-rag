

- Foundation
-  ProgressUserInfoKey 

Structure

# ProgressUserInfoKey

Keys for the user info dictionary that affect the autogenerated localized additional description string.

iOS 2.0+iPadOS 2.0+Mac Catalyst 13.0+macOS 10.0+tvOS 9.0+visionOS 1.0+watchOS 2.0+

``` source
struct ProgressUserInfoKey
```

## Discussion

Enhance the autogenerated description that localizedAdditionalDescription provides by including keys and related values in the user info dictionary. For example, if you provide the keys fileCompletedCountKey and fileTotalCountKey, the localizedAdditionalDescription method uses the values from those keys to provide strings showing the number of completed and total files.

## Topics

### Creating Keys

init(String)

Creates a new key using the specified string.

init(rawValue: String)

### Using General Keys

static let estimatedTimeRemainingKey: ProgressUserInfoKey

A key with a corresponding value that represents the time remaining, in seconds.

static let throughputKey: ProgressUserInfoKey

A key with a corresponding value that indicates the speed of data processing, in bytes per second.

### Using File Operation Keys

static let fileAnimationImageKey: ProgressUserInfoKey

A key with a corresponding value that is an image, typically an icon to represent the file.

static let fileAnimationImageOriginalRectKey: ProgressUserInfoKey

A key with a corresponding value that indicates the starting location of the image onscreen.

static let fileCompletedCountKey: ProgressUserInfoKey

A key with a corresponding value that represents the number of completed files.

static let fileIconKey: ProgressUserInfoKey

A key with a corresponding value that must be an image, typically an icon to represent the file.

static let fileOperationKindKey: ProgressUserInfoKey

A key with a corresponding value that indicates the kind of file operation a progress object represents.

static let fileTotalCountKey: ProgressUserInfoKey

A key with a corresponding value that represents the total number of files within a file operation.

static let fileURLKey: ProgressUserInfoKey

A key with a corresponding value that represents the file URL of a file operation for the progress object.

## Relationships

### Conforms To

- Equatable
- Hashable
- RawRepresentable
- Sendable

## See Also

### Inspecting Progress Information

var kind: ProgressKind?

An object that represents the kind of progress for the progress object.

var estimatedTimeRemaining: TimeInterval?

A value that indicates the estimated amount of time remaining to complete the progress.

var throughput: Int?

A value that represents the speed of data processing, in bytes per second.

func setUserInfoObject(Any?, forKey: ProgressUserInfoKey)

Sets a value in the user info dictionary.

var userInfo: [ProgressUserInfoKey : Any]

A dictionary of arbitrary values for the receiver.

struct ProgressKind

An object that represents the kind of progress.

