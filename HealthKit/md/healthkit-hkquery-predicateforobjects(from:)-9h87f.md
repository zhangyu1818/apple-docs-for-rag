

- HealthKit
- HKQuery
-  predicateForObjects(from:) 

Type Method

# predicateForObjects(from:)

Returns a predicate that matches all the objects that were created by any of the provided devices.

iOS 9.0+iPadOS 9.0+Mac Catalyst 13.0+macOS 13.0+visionOS 1.0+watchOS 2.0+

``` source
class func predicateForObjects(from devices: Set) -> NSPredicate
```

## Parameters 

`devices`  

A set of devices that have generated the data for objects stored in the HealthKit store.

## Return Value

A predicate that matches all the objects that store data generated by any of the provided devices.

## Discussion

When creating the device objects for this predicate, only pass in values for the parameters you need for your query. HealthKit returns all the devices that match the non-`nil` parameters. This gives you a great deal of control when it comes to fine tuning your query. For example, setting the `localIdentifier` and the `firmwareVersion` parameters lets you query for all the samples generated by a specific device running a specific version of the firmware. Just setting the `manufacturer` and `model` casts a much broader net.

The following sample uses both the convenience method and a predicate format string to create equivalent predicates.

- Swift
- Objective-C

```
let fromDevices = HKQuery.predicateForObjectsFromDevices(devices)

let explicitFromDevices =
    NSPredicate(format: "%K IN %@", HKPredicateKeyPathDevice, devices)
```

```
NSPredicate *fromDevices = [HKQuery predicateForObjectsFromDevices:devices];

NSPredicate *explicitFromDevices = [NSPredicate predicateWithFormat:@"%K IN %@",
                                    HKPredicateKeyPathDevice,
                                    devices];
```

## See Also

### Creating object predicates

class func predicateForObject(with: UUID) -> NSPredicate

Returns a predicate that matches an object with the specified universally unique identifier (UUID).

class func predicateForObjects(with: Set&lt;UUID>) -> NSPredicate

Returns a predicate that matches the objects with the specified universally unique identifiers (UUIDs).

class func predicateForObjects(from: HKSource) -> NSPredicate

Returns a predicate that matches all the objects that were created by the provided source.

class func predicateForObjects(from: Set&lt;HKSource>) -> NSPredicate

Returns a predicate that matches all the objects that were created by any of the provided sources.

class func predicateForObjects(withDeviceProperty: String, allowedValues: Set&lt;String>) -> NSPredicate

Returns a predicate that matches all objects created by devices with the specified properties.

class func predicateForObjects(from: Set&lt;HKSourceRevision>) -> NSPredicate

Returns a predicate that matches all the objects that were created by any of the provided source revisions.

class func predicateForObjects(withMetadataKey: String) -> NSPredicate

Returns a predicate that matches any object whose metadata contains the provided key.

class func predicateForObjects(withMetadataKey: String, allowedValues: [Any]) -> NSPredicate

Returns a predicate that matches objects based on the provided metadata key and an array of target values.

class func predicateForObjects(withMetadataKey: String, operatorType: NSComparisonPredicate.Operator, value: Any) -> NSPredicate

Returns a predicate that matches objects based on the provided metadata key, value, and operator.

class func predicateForObjectsWithNoCorrelation() -> NSPredicate

Returns a predicate that matches all objects that are not associated with a HealthKit correlation.

