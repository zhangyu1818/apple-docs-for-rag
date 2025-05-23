

- Audio Toolbox
- AUParameterNode
-  token(byAddingParameterRecordingObserver:) 

Instance Method

# token(byAddingParameterRecordingObserver:)

Adds a recording observer for a single parameter or all parameters in a group.

iOS 9.0+iPadOS 9.0+Mac Catalyst 13.1+macOS 10.11+tvOS 9.0+visionOS 1.0+

``` source
func token(byAddingParameterRecordingObserver observer: @escaping AUParameterRecordingObserver) -> AUParameterObserverToken
```

## Parameters 

`observer`  

A block called to record parameter changes.

## Return Value

A token which can be passed to the removeParameterObserver(_:) or setValue(_:originator:) methods.

## Discussion

A host can use a recording observer to capture a series of changes to a parameter value as generated by a UI gesture. Unlike a non-recording observer, these callbacks are not throttled.

This block is called in an arbitrary thread context and it is responsible for thread-safety. It must not make any calls to add or remove other observers, including itself, as this will deadlock.

An audio unit should interact with the parameter node via the implementorValueObserver and implementorValueProvider properties.

## See Also

### Observers

func token(byAddingParameterObserver: AUParameterObserver) -> AUParameterObserverToken

Adds an observer for a single parameter or all parameters in a group.

func token(byAddingParameterAutomationObserver: AUParameterAutomationObserver) -> AUParameterObserverToken

func removeParameterObserver(AUParameterObserverToken)

Remove a specific parameter observer.

