

- RealityKit
- ObjectCaptureView
-  keyframeAnimator(initialValue:repeating:content:keyframes:) 

Instance Method

# keyframeAnimator(initialValue:repeating:content:keyframes:)

Loops the given keyframes continuously, updating the view using the modifiers you apply in `body`.

RealityKitSwiftUIiOS 17.0+iPadOS 17.0+macOS 14.0+tvOS 17.0+watchOS 10.0+

``` source
nonisolated
func keyframeAnimator(
    initialValue: Value,
    repeating: Bool = true,
    @ViewBuilder content: @escaping (PlaceholderContentView, Value) -> some View,
    @KeyframesBuilder keyframes: @escaping (Value) -> some Keyframes
) -> some View
```

## Parameters 

`initialValue`  

The initial value that the keyframes will animate from.

`repeating`  

Whether the keyframes are currently repeating. If false, the value at the beginning of the keyframe timeline will be provided to the content closure.

`content`  

A view builder closure that takes two parameters. The first parameter is a proxy value representing the modified view. The second parameter is the interpolated value generated by the keyframes.

`keyframes`  

Keyframes defining how the value changes over time. The current value of the animator is the single argument, which is equal to `initialValue` when the view first appears, then is equal to the end value of the previous keyframe animation on subsequent calls.

## Discussion

Note that the `content` closure will be updated on every frame while animating, so avoid performing any expensive operations directly within `content`.

