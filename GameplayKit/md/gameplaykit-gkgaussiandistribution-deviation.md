

- GameplayKit
- GKGaussianDistribution
-  deviation 

Instance Property

# deviation

The standard deviation of the distribution (also called *sigma*).

iOS 9.0+iPadOS 9.0+Mac Catalyst 13.1+macOS 10.11+tvOS 9.0+visionOS 1.0+

``` source
var deviation: Float { get }
```

## Discussion

One deviation is defined such that 68.27% of values generated by the distribution are within one deviation of the mean value, 95% of generated values are within two deviations, and 100% of generated values are within three deviations. Values within two deviations of the mean have a 95% probabilty, and values within three deviations have a 100% probability.

Note

In the standard mathematical model of a Gaussian distribution, 99.7% of generated values are within three deviations of the mean and the distribution’s range is infinite. GameplayKit discards the extremely unlikely values more than three deviations from the mean in order to set finite limits on the distribution’s range.

This property is read-only—GameplayKit automatically calculates its value based on those of the inherited lowestValue and highestValue properties such that those values are each three deviations away from the mean (`deviation = (highest - lowest) / 6`).

## See Also

### Working with Characteristics of a Distribution

var mean: Float

The mean value of the distribution (also called the *expected value* or *median*).

