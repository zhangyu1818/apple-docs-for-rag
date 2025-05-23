

- HealthKit
-  HKLiveWorkoutBuilder 

Class

# HKLiveWorkoutBuilder

A builder object that constructs a workout incrementally based on live data from an active workout session.

macOSwatchOS 5.0+

``` source
class HKLiveWorkoutBuilder
```

## Mentioned in 

Running workout sessions

## Overview

Use a live workout builder to create an HKWorkout sample during an active HKWorkoutSession. For complete instructions on running workout sessions on Apple Watch, see Running workout sessions.

## Topics

### Configuring a live workout builder

var dataSource: HKLiveWorkoutDataSource?

A data source that provides live data from a workout session automatically.

var workoutSession: HKWorkoutSession?

The workout session created by the data source and associated with this builder.

### Monitoring and controlling the workout

var delegate: (any HKLiveWorkoutBuilderDelegate)?

The live builder’s delegate.

protocol HKLiveWorkoutBuilderDelegate

A protocol for monitoring live workout builders.

var currentWorkoutActivity: HKWorkoutActivity?

The current workout activity.

var shouldCollectWorkoutEvents: Bool

A Boolean value that determines whether the workout builder automatically adds events generated by the workout session.

### Accessing data

var elapsedTime: TimeInterval

The elapsed time for the workout based on the builder’s current contents, including pauses.

## Relationships

### Inherits From

- HKWorkoutBuilder

### Conforms To

- CVarArg
- CustomDebugStringConvertible
- CustomStringConvertible
- Equatable
- Hashable
- NSObjectProtocol
- Sendable

## See Also

### Sessions

Running workout sessions

Track a workout on Apple Watch.

Build a workout app for Apple Watch

Create your own workout app, quickly and easily, with HealthKit and SwiftUI.

Building a multidevice workout app

Mirror a workout from a watchOS app to its companion iOS app, and perform bidirectional communication between them.

class HKWorkoutSession

A session that tracks the user’s workout on Apple Watch.

class HKWorkoutConfiguration

An object that contains configuration information about a workout session.

enum HKWorkoutSessionState

A workout session’s state.

class HKLiveWorkoutDataSource

A data source that automatically provides live data from an active workout session.

