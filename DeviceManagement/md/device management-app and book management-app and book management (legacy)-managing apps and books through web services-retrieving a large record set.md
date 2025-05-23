

- Device Management
- App and Book Management
- App and Book Management (Legacy)
- Managing Apps and Books Through Web Services
-  Retrieving a Large Record Set 

Article

# Retrieving a Large Record Set

Efficiently work with large record sets.

## Overview

When the number of records in a response exceeds a server-controlled limit, the response will be batched. You can also retrieve only the records that have changed since your last query by using the `sinceModifiedToken`. Requests can be made in parallel to reduce the time it takes to retrieve the entire result set.

These concepts apply to the following endpoints:

- Get Licenses

- Get Users

### About SinceModifiedToken

The `sinceModifiedToken` may be used to keep your MDM system up-to-date with changes, without having to retrieve all records.

Once all records have been returned for a request, the server includes a `sinceModifiedToken` in the response. Your MDM server can pass this `sinceModifiedToken` in subsequent requests to get records modified since that token was generated.

Note

Even if no records are returned, the response still includes a `sinceModifiedToken` for use in subsequent requests.

### Batched Responses

A `batchToken` is used to retrieve multiple batches of records when the total number of records exceeds a limit.

To use a `batchToken`, your MDM server should do the following:

1.  Make an initial request with no `batchToken` (or `sinceModifiedToken`). This request returns all records associated with the provided sToken.

2.  If the number of records exceeds a server-controlled limit (on the order of several hundred), a `batchToken` value is included in the response, along with the first batch of records. Your MDM server should pass this `batchToken` value in a subsequent request to get the next batch of records. As long as additional batches remain, the server returns a new `batchToken` value in its response.

3.  Once all records have been returned for the request, the server includes a `sinceModifiedToken` value in the response. Your MDM server can pass this `sinceModifiedToken` in subsequent requests to get records modified since that token was generated. Again, if the number of modified records exceeds the limit, a `batchToken` will be included in the response, which can be used to get the next batch of modified records.

Note

Using `sinceModifiedToken` can result in batches with zero records in them. This is not an error or an end signal; just move to the next batch.

The following fields are used with batched responses:

| batchToken | A token used to signify which batch is being returned. The `batchToken` is generated by the server and can be several kilobytes in size. |
|----|----|
| batchCount | The number of records returned in the current batch. |
| totalBatchCount | The total number of round trips needed to get the complete result set. |
| overrideIndex | A value from `1` to the `totalBatchCount` value that specifies the batch of results to return. For requests with a value equal to the `totalBatchCount` value, the `sinceModifiedToken` value is returned. |
| totalCount | An estimate of the total number of records that will be returned. This value is only returned for requests that don’t include `batchToken` and the request that started the batch process. The actual number of records returned can be different by the time the client has finished retrieving all records. |

Tip

One of a set of sequential batch requests may return an error. It is also possible to get a response that includes no token, but also no error number. Because requests should return either a `batchToken` or `sinceModifiedToken`, do not interpret an error or the lack of a `batchToken` for an individual batch to mean that the last batch has been received. The last batch is signified by the inclusion of a `sinceModifiedToken`. If an individual batch request fails, the MDM server should retry the same batch using the same `batchToken`.

### Parallel Requests

Both the Get Licenses and Get Users endpoints can accept multiple requests in parallel, instead of sequentially, which can significantly reduce the amount of time required to request all licenses and users. You start by making an initial request to receive a `batchToken`. Subsequent requests can be submitted in parallel, by submitting the same `batchToken` and including an `overrideIndex` value from 1 to `totalBatchCount`. The request in which the `overrideIndex` value is equal to the `totalBatchCount` returns the new `sinceModifiedToken`.

For performance reasons, you shouldn’t submit more than five requests simultaneously.

