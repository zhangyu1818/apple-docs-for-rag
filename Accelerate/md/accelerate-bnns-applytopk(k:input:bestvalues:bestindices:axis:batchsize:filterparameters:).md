

- Accelerate
- BNNS
-  applyTopK(k:input:bestValues:bestIndices:axis:batchSize:filterParameters:) 

Type Method

# applyTopK(k:input:bestValues:bestIndices:axis:batchSize:filterParameters:)

Applies a top-k filter directly to an input.

iOS 14.0+iPadOS 14.0+Mac CatalystmacOS 11.0+tvOS 14.0+visionOSwatchOS 7.0+

``` source
static func applyTopK(
    k: Int,
    input: BNNSNDArrayDescriptor,
    bestValues: BNNSNDArrayDescriptor,
    bestIndices: BNNSNDArrayDescriptor,
    axis: Int,
    batchSize: Int,
    filterParameters: BNNSFilterParameters? = nil
) throws
```

## Parameters 

`k`  

The number of entries the operation finds.

`input`  

The descriptor of the input.

`bestValues`  

The descriptor of the k best values generated by the operation.

`bestIndices`  

The descriptor of the indices of the k best values generated by the operation.

`axis`  

The axis along which the operation finds top-k entries.

`batchSize`  

The number of input-output pairs to process.

`filterParameters`  

The filter runtime parameters.

## Discussion

Important

The input data type and best values data type must be `float`, and the best indices data type must be `int32`.

## See Also

### Related Documentation

func BNNSDirectApplyTopK(Int, Int, Int, UnsafePointer&lt;BNNSNDArrayDescriptor>, Int, UnsafeMutablePointer&lt;BNNSNDArrayDescriptor>, Int, UnsafeMutablePointer&lt;BNNSNDArrayDescriptor>?, Int, UnsafePointer&lt;BNNSFilterParameters>?) -> Int32

Applies a top-k filter directly to an input.

### Top-k layers

static func applyInTopK(k: Int, input: BNNSNDArrayDescriptor, testIndices: BNNSNDArrayDescriptor, output: BNNSNDArrayDescriptor, axis: Int, batchSize: Int, filterParameters: BNNSFilterParameters?) throws

Applies an in-top-k filter directly to an input.

