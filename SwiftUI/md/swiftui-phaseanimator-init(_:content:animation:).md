

- SwiftUI
- PhaseAnimator
-  init(\_:content:animation:) 

Initializer

# init(\_:content:animation:)

Cycles through a sequence of phases continuously, animating updates to a view on each phase change.

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

``` source
init(
    _ phases: some Sequence,
    @ViewBuilder content: @escaping (Phase) -> Content,
    animation: @escaping (Phase) -> Animation? = { _ in .default }
)
```

## Parameters 

`phases`  

The sequence of phases to cycle through. Ensure that the sequence isn’t empty. If it is, SwiftUI logs a runtime warning and also returns a visual warning as the output view.

`content`  

A view builder closure that takes the current phase as an input. Return a view that’s based on the current phase.

`animation`  

A closure that takes the current phase as input. Return the animation to use when transitioning to the next phase. If you return `nil`, the transition doesn’t animate. If you don’t set this parameter, SwiftUI uses a default animation.

## Discussion

When the phase animator first appears, this initializer renders the `content` closure using the first phase as input to the closure. The animator then begins immediately animating to the view produced by sending the second phase to the `content` closure using the animation returned from the `animation` closure. This procedure repeats for successive phases until reaching the last phase, after which the animator loops back to the first phase again.

## See Also

### Creating a phase animator

init(some Sequence&lt;Phase>, trigger: some Equatable, content: (Phase) -> Content, animation: (Phase) -> Animation?)

Cycles through a sequence of phases in response to changes in a specified value, animating updates to a view on each phase change.

