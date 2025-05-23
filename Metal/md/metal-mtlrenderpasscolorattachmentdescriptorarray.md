

- Metal
-  MTLRenderPassColorAttachmentDescriptorArray 

Class

# MTLRenderPassColorAttachmentDescriptorArray

An array of render pass color attachment descriptor objects.

iOS 8.0+iPadOS 8.0+Mac Catalyst 13.1+macOS 10.11+tvOSvisionOS 1.0+

``` source
class MTLRenderPassColorAttachmentDescriptorArray
```

## Topics

### Accessing the Description of a Color Attachment

subscript(Int) -> MTLRenderPassColorAttachmentDescriptor!

Returns the descriptor object for the specified color attachment.

## Relationships

### Inherits From

- NSObject

### Conforms To

- CVarArg
- CustomDebugStringConvertible
- CustomStringConvertible
- Equatable
- Hashable
- NSObjectProtocol

## See Also

### Configuring a Render Command Encoder

class MTLRenderPassDescriptor

A group of render targets that hold the results of a render pass.

class MTLRenderPassAttachmentDescriptor

A render target that serves as the output destination for pixels generated by a render pass.

class MTLRenderPassColorAttachmentDescriptor

A color render target that serves as the output destination for color pixels generated by a render pass.

struct MTLClearColor

An RGBA value used for a color pixel.

class MTLRenderPassDepthAttachmentDescriptor

A depth render target that serves as the output destination for depth pixels generated by a render pass.

enum MTLMultisampleDepthResolveFilter

Filtering options for controlling an MSAA depth resolve operation.

class MTLTileRenderPipelineColorAttachmentDescriptorArray

An array of color attachment descriptors for the tile render pipeline.

class MTLRenderPassStencilAttachmentDescriptor

A stencil render target that serves as the output destination for stencil pixels generated by a render pass.

enum MTLMultisampleStencilResolveFilter

Constants used to control the multisample stencil resolve operation.

class MTLRenderPassSampleBufferAttachmentDescriptorArray

An array of sample buffer attachments for a render pass.

class MTLRenderPassSampleBufferAttachmentDescriptor

A description of where to store GPU counter information at the start and end of a render pass.

