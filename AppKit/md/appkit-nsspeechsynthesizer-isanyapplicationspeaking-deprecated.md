

- AppKit
- NSSpeechSynthesizer
-  isAnyApplicationSpeaking Deprecated

Type Property

# isAnyApplicationSpeaking

A Boolean value indicating whether any application is currently speaking through the sound output device.

macOS 10.3–14.0Deprecated

``` source
class var isAnyApplicationSpeaking: Bool { get }
```

Deprecated

Use AVSpeechSynthesizer in AVFoundation instead

## Discussion

This property is true when another application is producing speech through the sound output device. You usually invoke this method to prevent your application from speaking over speech being generated by another application or system component.

