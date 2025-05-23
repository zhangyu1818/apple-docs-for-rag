

- ShaderGraph
- RealityKit
-  Image 2D LOD (RealityKit) 

ShaderGraph Node

# Image 2D LOD (RealityKit)

A texture with RealityKit properties and a explicit level of detail.

## Parameter Types

- Image 2D LOD (vector4f)
- Image 2D LOD (color4)
- Image 2D LOD (color3)

| Input                    | Type      |
|--------------------------|-----------|
| `File`                   | AssetPath |
| `U Wrap Mode`            | String    |
| `V Wrap Mode`            | String    |
| `Border Color`           | String    |
| `Mag Filter`             | String    |
| `Min Filter`             | String    |
| `Mip Filter`             | String    |
| `Max Anisotropy`         | Int32     |
| `Max Lod Clamp`          | Float     |
| `Min Lod Clamp`          | Float     |
| `Default`                | Vector4f  |
| `Texture Coordinates`    | Vector2f  |
| `Use MaterialX V Origin` | Bool      |
| `Lod`                    | Float     |
| `Offset`                 | Integer2  |

| Output | Type     |
|--------|----------|
| `Out`  | Vector4f |

| Input                    | Type      |
|--------------------------|-----------|
| `File`                   | AssetPath |
| `U Wrap Mode`            | String    |
| `V Wrap Mode`            | String    |
| `Border Color`           | String    |
| `Mag Filter`             | String    |
| `Min Filter`             | String    |
| `Mip Filter`             | String    |
| `Max Anisotropy`         | Int32     |
| `Max Lod Clamp`          | Float     |
| `Min Lod Clamp`          | Float     |
| `Default`                | Color4    |
| `Texture Coordinates`    | Vector2f  |
| `Use MaterialX V Origin` | Bool      |
| `Lod`                    | Float     |
| `Offset`                 | Integer2  |

| Output | Type   |
|--------|--------|
| `Out`  | Color4 |

| Input                    | Type      |
|--------------------------|-----------|
| `File`                   | AssetPath |
| `U Wrap Mode`            | String    |
| `V Wrap Mode`            | String    |
| `Border Color`           | String    |
| `Mag Filter`             | String    |
| `Min Filter`             | String    |
| `Mip Filter`             | String    |
| `Max Anisotropy`         | Int32     |
| `Max Lod Clamp`          | Float     |
| `Min Lod Clamp`          | Float     |
| `Default`                | Color3    |
| `Texture Coordinates`    | Vector2f  |
| `Use MaterialX V Origin` | Bool      |
| `Lod`                    | Float     |
| `Offset`                 | Integer2  |

| Output | Type   |
|--------|--------|
| `Out`  | Color3 |

## Parameter descriptions

`File`  
The image file to use for the texture.

`U Wrap Mode`  
The way the node handles *U* values outside of the range of `0-1`. The default value is `clamp_to_edge`.

`V Wrap Mode`  
The way the node handles *V* values outside of the range of `0-1`. The default value is `clamp_to_edge`.

`Border Color`  
A color that fills in areas of a material’s surface not covered by the material property’s image contents. The default value is `transparent_black`.

`Mag Filter`  
The magnification filtering mode the node uses to render the image contents at a size larger than the original image. For example, the texture coordinates at a point near the camera may correspond to a small fraction of a pixel in the texture image. This node uses the `Mag Filter` to determine the color of the sampled texel at that point. The default value is `linear`.

`Min Filter`  
The minimizing filtering mode the node uses to render the image contents at a size smaller than the original image. For example, the texture coordinates at a point far from the camera may correspond to an area of several pixels in the texture image. This node uses the `Min Filter` to determine the color of the sampled texel at that point. The default value is `linear`.

`Mip Filter`  
The mipmap filtering mode the node uses when rendering the image contents using mipmapping. Useful when rendering an image at a size smaller than the original image. If the value of this parameter is `None`, the node won’t use mipmapping. The default value is `linear`.

`Max Anisotropy`  
The amount of anisotropic texture filtering applied when rendering the texture’s image contents. Used when rendering the image contents at an extreme angle relative to the camera. This parameter is used only in conjunction with mipmapping, so it only has an effect if `Mip Filter` isn’t `None`. The default value is `1`.

`Max Lod Clamp`  
The maximum level of detail allowed for the rendered image contents. As an object gets closer to the camera, the level of detail used to render the texture of that object increases up to the maximum defined by this parameter. The default value is `65504`.

`Min Lod Clamp`  
The minimum level of detail allowed for the rendered image contents. As an object gets farther from the camera, the level of detail used to render the texture of that object decreases to the minimum defined by this parameter. The default value is `0`.

`Default`  
The default value to use if the ​`File​` parameter fails to resolve.

`Texture Coordinates`  
The 2D coordinate at which the data is read in order to map the texture onto a surface. The default is the current *UV* coordinates, in which *U* is the horizontal axis and *V* is the vertical axis.

`Lod`  
The specific LOD level that the node will sample from.

`Offset`  
The integer values added to the texture coordinates before looking up each pixel. The value must be within the range `-8-7`. The default value is `0`.

## Discussion

The Image 2D LOD node produces a texture using the contents of the image file specified in the `File` parameter. It has a multitude of parameters that affect the properties of the rendered textures.

For the wrap mode parameters, the possible values are:

`clamp_to_border`  
The node sets texture coordinates outside the normal range to the color specified by the `Border Color` parameter.

`clamp_to_edge`  
The node clamps texture coordinates outside the normal range to the normal range. The node will set any values greater than `1` to `1`, and any values less than `0` to `0`. This means the color’s on the edge of the image will extend to fill the rest of the texture.

`clamp_to_zero`  
The node sets texture coordinates outside the normal range to a color of value of `0` or black. This is equivalent to the `clamp_to_border` option with a border color of `transparent_black`.

`mirrored_repeat`  
The node mirrors texture coordinates outside the normal range.

`repeat`  
The node will cause texture coordinates outside the normal range to “wrap around.” This behavior is effectively equivalent to the node applying modulo 1 to the coordinates.

Warning

You can only use the clamp-to-zero option if the `Border Color` parameter is set to `transparent_black`; otherwise, the behavior of the node is undefined.

For the `Mag Filter` and `Min Filter` parameters, the possible values are:

`linear`  
The filter uses linear interpolation of the closest values in order to determine the rendered contents.

`nearest`  
The filter uses the nearest value in order to determine the rendered contents.

The `Mip Filter` parameter has the same possible values, with the addition of the option to allow for the value of `None`, which specifies that mipmapping isn’t used.

For an example on how to use this node, see the bottom of the Image 2D (RealityKit) node page.

## See Also

### Nodes

Unlit Surface (RealityKit)

A surface shader that defines properties for a RealityKit Unlit material.

PBR Surface (RealityKit)

A surface shader that defines properties for a RealityKit Physically Based Rendering material.

Occlusion Surface (RealityKit)

A surface shader that defines properties for a RealityKit Occlusion material that does not receive dynamic lighting.

Shadow Receiving Occlusion Surface (RealityKit)

A surface shader that defines properties for a RealityKit Occlusion material that receives dynamic lighting.

View Direction (RealityKit)

A vector from a position in the scene to the view reference point.

Camera Position (RealityKit)

The position of the camera in the scene.

Geometry Modifier Model To World (RealityKit)

The model-to-world transformation Matrix4x4 (Float).

Geometry Modifier World To Model (RealityKit)

The world-to-model transformation Matrix4x4 (Float).

Geometry Modifier Normal To World (RealityKit)

The normal-to-world transformation Matrix3x3 (Float).

Geometry Modifier Model To View (RealityKit)

The model-to-view transformation Matrix4x4 (Float).

Geometry Modifier View To Projection (RealityKit)

The view-to-projection transformation Matrix4x4 (Float).

Geometry Modifier Projection To View (RealityKit)

The projection-to-view transformation Matrix4x4 (Float).

Geometry Modifier Vertex ID (RealityKit)

The integer index of the vertex.

Surface Model To World (RealityKit)

The model-to-world transformation Matrix4x4 (Float).

Surface Model To View (RealityKit)

The model-to-view transformation Matrix4x4 (Float).

