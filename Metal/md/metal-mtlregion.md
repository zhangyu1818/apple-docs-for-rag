

- Metal
-  MTLRegion 

Structure

# MTLRegion

The bounds for a subset of an object’s elements.

iOSiPadOSMac CatalystmacOStvOSvisionOS

``` source
struct MTLRegion
```

## Mentioned in 

Converting Between Pixel Regions and Sparse Tile Regions

## Overview

Metal has many object types that represent arrays of discrete elements. For example, a texture has an array of pixel elements, and a thread grid has an array of computational threads. Use MTLRegion instances to describe subsets of these objects.

The origin is the front upper-left corner of the region, and its extents go towards the back lower-right corner. Conceptually, when using a MTLRegion instance to describe a subset of an object, treat the object as a 3D array of elements, even if it has fewer dimensions. For a 2D object, set the z coordinate of the origin to `0` and the depth to `1`. For a 1D object, set the y and z coordinates of the origin to `0` and the height and depth to `1`.

## Topics

### Creating Regions

init()

Initializes a new region.

init(origin: MTLOrigin, size: MTLSize)

Initializes a new region with the specified origin and size.

func MTLRegionMake1D(Int, Int) -> MTLRegion

Creates a 3D representation of a 1D region.

func MTLRegionMake2D(Int, Int, Int, Int) -> MTLRegion

Creates a 3D representation of a 2D region.

func MTLRegionMake3D(Int, Int, Int, Int, Int, Int) -> MTLRegion

Creates a 3D region.

### Getting and Setting Region Information

var origin: MTLOrigin

The coordinates of the front upper-left corner of the region.

var size: MTLSize

The dimensions of the region.

## Relationships

### Conforms To

- BitwiseCopyable
- Sendable

## See Also

### Indirect Compute Commands

protocol MTLIndirectComputeCommand

A compute command in an indirect command buffer.

struct MTLSize

The dimensions of an object.

struct MTLOrigin

The coordinates for the front upper-left corner of a region.

struct MTLStageInRegionIndirectArguments

The data layout required for the arguments needed to specify the stage-in region.

struct MTLDispatchThreadgroupsIndirectArguments

The data layout required for arguments needed to specify the size of threadgroups.

