

- GameplayKit
-  GKConstantNoiseSource 

Class

# GKConstantNoiseSource

A procedural noise generator that outputs a field of a single constant value.

iOS 10.0+iPadOS 10.0+Mac Catalyst 13.1+macOS 10.12+tvOS 10.0+visionOS 1.0+

``` source
class GKConstantNoiseSource
```

## Overview

Constant noise can be useful as an input to GKNoise methods that create noise by combining other noise objects through various operations. For example, when using the displaceWithNoises(x:y:z:) method you can pass constant noise for some parameters and non-constant noise for other parameters, resulting in a variable displacement along one axis but constant or no displacement along the others.

Like all GKNoiseSource subclasses, a constant noise source represents a noise generation algorithm and its parameters. To make use of a noise source, first create GKNoise object from it (and optionally apply operations to that noise object or combine it with other noise objects). Then create a GKNoiseMap object from your noise object, generating a concrete field of values that you can sample from directly or visualize using the SKTexture or `SKTileMap` class.

## Topics

### Creating a Noise Source

init(value: Double)

Initializes a noise source with the specified constant value.

class func constantNoise(withValue: Double) -> Self

Creates a noise source with the specified constant value.

### Managing Noise Generation Parameters

var value: Double

The constant value for the generated noise.

## Relationships

### Inherits From

- GKNoiseSource

### Conforms To

- CVarArg
- CustomDebugStringConvertible
- CustomStringConvertible
- Equatable
- Hashable
- NSObjectProtocol

## See Also

### Procedural Noise

class GKNoiseSource

The abstract superclass for procedural noise generators.

class GKNoise

A representation of procedural noise, generated by a noise source, that you can use to process, transform, or combine noise.

class GKNoiseMap

A sample of procedural noise data from which you can read noise values directly or create noise textures.

class GKCoherentNoiseSource

The abstract superclass for procedural noise generators that create coherent noise.

class GKBillowNoiseSource

A procedural noise generator whose output is a type of fractal coherent noise with smooth features.

class GKPerlinNoiseSource

A procedural noise generator whose output is a type of fractal coherent noise resembling natural phenomena such as clouds and terrain.

class GKRidgedNoiseSource

A procedural noise generator whose output is a type of multifractal coherent noise with sharply defined features.

class GKVoronoiNoiseSource

A procedural noise generator whose output (also called Worley noise or cellular noise) divides space into discrete cells surrounding random seed points.

class GKCylindersNoiseSource

A procedural noise generator whose output is a 3D field of concentric cylindrical shells.

class GKSpheresNoiseSource

A procedural noise generator whose output is a 3D field of concentric spherical shells.

class GKCheckerboardNoiseSource

A procedural noise generator whose output is an alternating square pattern.

