

- ProximityReader
-  MobileDocumentReader 

Class

# MobileDocumentReader

An object for configuring mobile document reading on the current device.

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+

``` source
final class MobileDocumentReader
```

## Mentioned in 

Adopting the Verifier API in your iPhone app

## Overview

After creating the `MobileDocumentReader` object, call prepare(using:) to prepare the device for mobile document reading. Use the returned MobileDocumentReaderSession object to read mobile documents.

You can optionally display your brand’s name and logo during a mobile document read. To do this, your server needs to generate a reader token, then pass the token as an argument to the prepare(using:) method.

## Topics

### Creating a mobile document reader

init()

Creates a mobile document reader.

### Getting the feature availability

static var isSupported: Bool

A Boolean value that indicates whether the device supports mobile document reading.

### Preparing the device for reading mobile documents

func prepare(using: MobileDocumentReader.Token?) async throws -> MobileDocumentReaderSession

Configures the device to read mobile documents.

struct Token

A reader token generated by your server.

### Retrieving the reader configuration

var configuration: MobileDocumentReader.Configuration

The configuration of the mobile document reader.

struct Configuration

A type that represents the configuration of the mobile document reader.

## Relationships

### Conforms To

- Sendable

## See Also

### Mobile document reader

Adopting the Verifier API in your iPhone app

Configure and test ID Verifier support in your app for reading mobile documents.

Generating reader tokens for the Verifier API

Configure your server to generate reader tokens to prepare a device for mobile document reading.

Checking IDs with the Verifier API

Read and verify mobile driver’s license information without any additional hardware.

class MobileDocumentReaderSession

The object you use to start reading a mobile document.

