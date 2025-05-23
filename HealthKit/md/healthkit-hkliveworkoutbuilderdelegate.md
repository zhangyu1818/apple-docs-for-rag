

- HealthKit
-  HKLiveWorkoutBuilderDelegate 

Protocol

# HKLiveWorkoutBuilderDelegate

A protocol for monitoring live workout builders.

macOSwatchOS 5.0+

``` source
protocol HKLiveWorkoutBuilderDelegate : NSObjectProtocol
```

## Mentioned in 

Running workout sessions

## Topics

### Tracking Live Data

func workoutBuilder(HKLiveWorkoutBuilder, didCollectDataOf: Set&lt;HKSampleType>)

Tells the delegate that new data has been added to the builder.

**Required**

func workoutBuilderDidCollectEvent(HKLiveWorkoutBuilder)

Tells the delegate that a new event has been added to the builder.

**Required**

func workoutBuilder(HKLiveWorkoutBuilder, didBegin: HKWorkoutActivity)

Tells the delegate that a new workout activity has started.

func workoutBuilder(HKLiveWorkoutBuilder, didEnd: HKWorkoutActivity)

Tells the delegate that the current workout activity has ended.

## Relationships

### Inherits From

- NSObjectProtocol

## See Also

### Monitoring and controlling the workout

var delegate: (any HKLiveWorkoutBuilderDelegate)?

The live builder’s delegate.

var currentWorkoutActivity: HKWorkoutActivity?

The current workout activity.

var shouldCollectWorkoutEvents: Bool

A Boolean value that determines whether the workout builder automatically adds events generated by the workout session.

