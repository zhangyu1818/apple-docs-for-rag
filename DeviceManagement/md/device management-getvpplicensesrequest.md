

- Device Management
-  GetVppLicensesRequest 

Object

# GetVppLicensesRequest

The request for licenses.

Device Assignment ServicesVPP License Management

``` source
object GetVppLicensesRequest
```

## Properties

`adamId`

`string`

The unique identifier for a product in the iTunes Store.

`assignedOnly`

`boolean`

If `true`, returns only licenses assigned to a user or device. For best performance, set `assignedOnly` to `true`; otherwise, all licenses are returned.

`batchToken`

`string`

A token that signifies which batch is being returned. A `batchToken` value is generated by the server and can be several kilobytes in size.For an initial request that doesn’t include `batchToken` or `sinceModifiedToken`, a `batchToken` value is returned if the number of results exceeds a server-controlled limit. Subsequent requests must include `batchToken`. As long as additional batches remain, the server returns a new `batchToken` value in its response.

See Batched Responses for more information.

`deviceAssignedOnly`

`boolean`

If `true`, returns only licenses currently assigned to a device. Default is `false`.

`overrideIndex`

`int32`

A value from 1 to the `totalBatchCount` value that specifies the batch of results to return. For requests with a value equal to the `totalBatchCount` value, the `sinceModifiedToken` value is returned.

`pricingParam`

`string`

The quality of a product in the iTunes Store. If a pricing parameter is specified, only records with that parameter are included in the results. Possible values are:

`STDQ` = Standard quality.

`PLUS` = High quality.

If `pricingParam` is specified, `adamId` must be specified. Otherwise, the pricing parameter is ignored.

`serialNumber`

`string`

If specified, returns only licenses assigned to the given serial number.

`sinceModifiedToken`

`string`

A token that marks a place in time. After all records have been returned for a request, the server includes a `sinceModifiedToken` value in the response. Use it in subsequent requests to get licenses that have been modified since the token was generated.

See About SinceModifiedToken for more information.

`sToken`

`string`

 (Required) 

The authentication token. For more information, see Authentication.

`userAssignedOnly`

`boolean`

If `true`, returns only licenses currently assigned to a user. Default is `false`.

## Discussion

The `batchToken` and `sinceModifiedToken` encode whether `adamId` and `pricingParam` were originally passed; therefore, if the `batchToken` or `sinceModifiedToken` is present on the request, the `adamId` and `pricingParam` fields (if passed) are ignored.

## See Also

### Request and Response

object GetVppLicensesResponse

The response with the licenses.

