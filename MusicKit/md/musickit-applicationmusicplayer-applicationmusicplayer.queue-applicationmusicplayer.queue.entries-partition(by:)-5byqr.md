

- MusicKit
- ApplicationMusicPlayer
- ApplicationMusicPlayer.Queue
- ApplicationMusicPlayer.Queue.Entries
-  partition(by:) 

Instance Method

# partition(by:)

Reorders the elements of the collection such that all the elements that match the given predicate are after all the elements that don’t match.

MusicKitSwiftiOS 15.0+iPadOS 15.0+Mac Catalyst 15.0+macOS 12.0+tvOS 15.0+visionOS 1.0+

``` source
mutating func partition(by belongsInSecondPartition: (Self.Element) throws -> Bool) rethrows -> Self.Index
```

## Parameters 

`belongsInSecondPartition`  

A predicate used to partition the collection. All elements satisfying this predicate are ordered after all elements not satisfying it.

## Return Value

The index of the first element in the reordered collection that matches `belongsInSecondPartition`. If no elements in the collection match `belongsInSecondPartition`, the returned index is equal to the collection’s `endIndex`.

## Discussion

After partitioning a collection, there is a pivot index `p` where no element before `p` satisfies the `belongsInSecondPartition` predicate and every element at or after `p` satisfies `belongsInSecondPartition`. This operation isn’t guaranteed to be stable, so the relative ordering of elements within the partitions might change.

In the following example, an array of numbers is partitioned by a predicate that matches elements greater than 30.

```
var numbers = [30, 40, 20, 30, 30, 60, 10]
let p = numbers.partition(by: { $0 > 30 })
// p == 5
// numbers == [30, 10, 20, 30, 30, 60, 40]
```

The `numbers` array is now arranged in two partitions. The first partition, `numbers[..

```
let first = numbers[..

Note that the order of elements in both partitions changed. That is, `40` appears before `60` in the original collection, but, after calling `partition(by:)`, `60` appears before `40`.

Complexity

O(*n*), where *n* is the length of the collection.

