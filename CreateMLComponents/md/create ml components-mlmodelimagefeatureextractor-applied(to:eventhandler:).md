

- Create ML Components
- MLModelImageFeatureExtractor
-  applied(to:eventHandler:) 

Instance Method

# applied(to:eventHandler:)

Uses the CoreML model to create image features from the input pixel buffer.

iOS 16.0+iPadOS 16.0+Mac Catalyst 16.0+macOS 13.0+tvOS 16.0+visionOS 1.0+

``` source
func applied(
    to input: CIImage,
    eventHandler: EventHandler? = nil
) async throws -> MLShapedArray
```

## Parameters 

`input`  

An image.

`eventHandler`  

An event handler.

## Return Value

`ImageFeatures` generated by passing the `pixelBuffer` through the `model`.

## See Also

### Applying

enum Error

CoreML Extraction error.

