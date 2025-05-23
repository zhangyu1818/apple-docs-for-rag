

- SwiftUI
- KeyframeAnimator
-  init(initialValue:repeating:content:keyframes:) 

Initializer

# init(initialValue:repeating:content:keyframes:)

Loops the given keyframes continuously, updating the view using the modifiers you apply in `body`.

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

``` source
init(
    initialValue: Value,
    repeating: Bool = true,
    @ViewBuilder content: @escaping (Value) -> Content,
    @KeyframesBuilder keyframes: @escaping (Value) -> KeyframePath
)
```

## Parameters 

`initialValue`  

The initial value that the keyframes will animate from.

`repeating`  

Whether the keyframes are currently repeating. If false, the value at the beginning of the keyframe timeline will be provided to the content closure.

`content`  

A view builder closure that takes the interpolated value generated by the keyframes as its single argument.

`keyframes`  

Keyframes defining how the value changes over time. The current value of the animator is the single argument, which is equal to `initialValue` when the view first appears, then is equal to the end value of the previous keyframe animation on subsequent calls.

## Discussion

Note that the `content` closure will be updated on every frame while animating, so avoid performing any expensive operations directly within `content`.

## See Also

### Creating a phase animator

init(initialValue: Value, trigger: some Equatable, content: (Value) -> Content, keyframes: (Value) -> KeyframePath)

Plays the given keyframes when the given trigger value changes, updating the view using the modifiers you apply in `body`.

