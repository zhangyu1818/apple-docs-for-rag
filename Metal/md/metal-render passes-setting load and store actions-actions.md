

- Metal
- Render Passes
-  Setting Load and Store Actions 

Article

# Setting Load and Store Actions

Set actions that define how a render pass loads and stores a render target.

## Overview

MTLLoadAction and MTLStoreAction values allow you to define how a render pass loads and stores your MTLRenderPassAttachmentDescriptor objects. By choosing appropriate actions for your render targets, you can avoid costly and unnecessary work at the start (load) or end (store) of a render pass.

Set a render targetʼs texture on its texture property. Then, set its actions on its loadAction and storeAction properties:

- Swift
- Objective-C

```
let renderPassDescriptor = MTLRenderPassDescriptor()

// Color render target
renderPassDescriptor.colorAttachments[0].texture = colorTexture
renderPassDescriptor.colorAttachments[0].loadAction = .clear
renderPassDescriptor.colorAttachments[0].storeAction = .store

// Depth render target
renderPassDescriptor.colorAttachments[0].texture = depthTexture
renderPassDescriptor.colorAttachments[0].loadAction = .dontCare
renderPassDescriptor.colorAttachments[0].storeAction = .dontCare

// Stencil render target
renderPassDescriptor.colorAttachments[0].texture = stencilTexture
renderPassDescriptor.colorAttachments[0].loadAction = .dontCare
renderPassDescriptor.colorAttachments[0].storeAction = .dontCare
```

```
MTLRenderPassDescriptor *renderPassDescriptor = [MTLRenderPassDescriptor renderPassDescriptor];

// Color render target
renderPassDescriptor.colorAttachments[0].texture = colorTexture;
renderPassDescriptor.colorAttachments[0].loadAction = MTLLoadActionClear;
renderPassDescriptor.colorAttachments[0].storeAction = MTLStoreActionStore;

// Depth render target
renderPassDescriptor.depthAttachment.texture = depthTexture;
renderPassDescriptor.depthAttachment.loadAction = MTLLoadActionDontCare;
renderPassDescriptor.depthAttachment.storeAction = MTLStoreActionDontCare;

// Stencil render target
renderPassDescriptor.stencilAttachment.texture = stencilTexture;
renderPassDescriptor.stencilAttachment.loadAction = MTLLoadActionDontCare;
renderPassDescriptor.stencilAttachment.storeAction = MTLStoreActionDontCare;
```

### Choose a Load Action

Several options are available, depending on which of the following scenarios describes your render targetʼs loading needs.

**You donʼt need the previous contents of the render target and you render to all of its pixels.** Choose MTLLoadAction.dontCare. This action incurs no cost, and pixel values are always undefined at the start of the render pass.

**You donʼt need the previous contents of the render target and you render to only some of its pixels.** Choose MTLLoadAction.clear. This action incurs the cost of writing the render targetʼs clear value to each pixel.

**You do need the previous contents of the render target and you render to only some of its pixels.** Choose MTLLoadAction.load. This action incurs the cost of loading the previous values of each pixel from memory. This action is significantly slower than MTLLoadAction.dontCare or MTLLoadAction.clear.

Note

You canʼt choose MTLLoadAction.load for a memoryless render target because it isnʼt backed by system memory. For more information about memoryless render targets, see Choosing a Resource Storage Mode for Apple GPUs.

### Choose a Store Action

Several options are available, depending on which of the following scenarios describes your render targetʼs storage needs.

**You donʼt need to preserve the contents of the render target.** Choose MTLStoreAction.dontCare. This action incurs no cost, and pixel values are always undefined at the end of the render pass. Choose this action for intermediary render targets that you use within the render pass, but you donʼt need afterward. This is typically the correct action for depth and stencil render targets.

**You do need to preserve the contents of the render target.** Choose MTLStoreAction.store. This action incurs the cost of storing the values of each pixel to memory. This is always the correct action for drawables.

**Your render target is a multisample texture.** When you perform multisampling, you decide whether to store the render targetʼs multisampled or resolved data. Multisampled data is stored in the render targetʼs texture property. Resolved data is stored in the render targetʼs resolveTexture property. Refer to this table to choose a store action when multisampling:

| Multisampled data stored | Resolved data stored | Resolve texture required | Required store action |
|----|----|----|----|
| Yes | Yes | Yes | MTLStoreAction.storeAndMultisampleResolve |
| Yes | No | No | MTLStoreAction.store |
| No | Yes | Yes | MTLStoreAction.multisampleResolve |
| No | No | No | MTLStoreAction.dontCare |

To store and resolve a multisample texture in a single render pass, always choose the MTLStoreAction.storeAndMultisampleResolve action and use a single render command encoder.

**You need to defer your storage choice.** In some cases, you might not know which store action to use for a particular render target until you gather more render pass information. To defer your store action choice, set the temporary MTLStoreAction.unknown value when you create your MTLRenderPassAttachmentDescriptor object. Setting an unknown store action may avoid potential costs incurred by setting another store action prematurely. However, you must specify a valid store action before you finish encoding your render pass; otherwise, an error occurs.

Note

You canʼt choose MTLStoreAction.store or MTLStoreAction.storeAndMultisampleResolve for a memoryless render target because it isnʼt backed by system memory. For more information about memoryless render targets, see Choosing a Resource Storage Mode for Apple GPUs.

### Evaluate Actions Between Render Passes

You can use the same render targets across multiple render passes. Several load and store combinations are possible for the same render target between any two render passes, depending on which of the following scenarios describes your render targetʼs needs from one render pass to another.

**You donʼt need the previous contents of a render target in the next render pass.** In the first render pass, choose MTLStoreAction.dontCare to avoid storing the contents of the render target. In the second render pass, choose MTLLoadAction.dontCare or MTLLoadAction.clear to avoid loading the contents of the render target.

**You do need the previous contents of a render target in the next render pass.** In the first render pass, choose MTLStoreAction.store, MTLStoreAction.multisampleResolve, or MTLStoreAction.storeAndMultisampleResolve to store the contents of the render target. In the second render pass, choose MTLLoadAction.load to load the contents of the render target.

## See Also

### Applying Rendering Techniques

Using a Render Pipeline to Render Primitives

Render a simple 2D triangle.

Customizing Render Pass Setup

Render into an offscreen texture by creating a custom render pass.

Improving Rendering Performance with Vertex Amplification

Run draw commands that render to different outputs using the same vertex data multiple times.

