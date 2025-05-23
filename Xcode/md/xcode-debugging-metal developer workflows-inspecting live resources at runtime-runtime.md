

- Xcode
- Debugging
- Metal developer workflows
-  Inspecting live resources at runtime 

Article

# Inspecting live resources at runtime

Validate your resources by viewing the contents of your textures and buffers while debugging your Metal app.

## Overview

You can preview contents of textures and buffers while debugging your app in Xcode by pausing on a breakpoint, inspecting a variable that references the resource, and then clicking the Preview button. This is one quick way to validate that your resources have the correct contents while debugging at runtime.

Important

If you disable GPU Frame Capture, you can’t inspect resource content while your app is running. See Capturing a Metal workload in Xcode to learn how to reenable it.

### Inspect your textures and buffers

First, pause the app inside a scope that contains a variable referencing the resource. You can achieve this by setting a breakpoint on a line that references the resource. To set a breakpoint, click the line number to the left of the source editor. The example below shows a breakpoint for the line where `_skyMap` is bound to the render encoder:

Then, when yor app pauses at the breakpoint, move the pointer over the variable referencing the resource to reveal the Value inspector.

Finally, click the Preview button to show the contents of the resource.

If the resource is a texture and has multiple slices, like the sky map above, you can drag the slider at the bottom of the Preview popover to see each slice. If the resource has any unexpected values, you can investigate further with the Metal debugger (see Investigating visual artifacts).

## See Also

### Runtime diagnostics

Validating your app’s Metal API usage

Catch runtime issues in your Metal app using API Validation.

Validating your app’s Metal shader usage

Catch common shader runtime issues using Shader Validation while your app is running.

Monitoring your Metal app’s graphics performance

Catch performance issues using the Metal Performance HUD while your app is running.

