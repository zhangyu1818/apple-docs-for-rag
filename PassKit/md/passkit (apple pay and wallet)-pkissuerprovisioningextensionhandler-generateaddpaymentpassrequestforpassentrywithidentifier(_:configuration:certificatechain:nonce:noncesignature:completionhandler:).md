

- PassKit (Apple Pay and Wallet)
- PKIssuerProvisioningExtensionHandler
-  generateAddPaymentPassRequestForPassEntryWithIdentifier(\_:configuration:certificateChain:nonce:nonceSignature:completionHandler:) 

Instance Method

# generateAddPaymentPassRequestForPassEntryWithIdentifier(\_:configuration:certificateChain:nonce:nonceSignature:completionHandler:)

Creates an object with the data the system needs to add a card to Apple Pay.

iOS 14.0+iPadOS 14.0+Mac Catalyst 14.0+visionOS 1.0+

``` source
func generateAddPaymentPassRequestForPassEntryWithIdentifier(
    _ identifier: String,
    configuration: PKAddPaymentPassRequestConfiguration,
    certificateChain certificates: [Data],
    nonce: Data,
    nonceSignature: Data,
    completionHandler completion: @escaping (PKAddPaymentPassRequest?) -> Void
)
```

``` source
func generateAddPaymentPassRequestForPassEntryWithIdentifier(
    _ identifier: String,
    configuration: PKAddPaymentPassRequestConfiguration,
    certificateChain certificates: [Data],
    nonce: Data,
    nonceSignature: Data
) async -> PKAddPaymentPassRequest?
```

## Parameters 

`identifier`  

The value that you use to identify the card.

`configuration`  

The configuration the system uses to add a secure pass.

`certificates`  

An array of data objects. Each object contains a DER encoded X.509 certificate, with the leaf first and root last. You must download the root CA to validate the entire chain.

`nonce`  

A one-time nonce value generated by Apple’s servers. You must include this signature nonce in the add-payment request’s encrypted data.

`nonceSignature`  

The device-specific signature for the nonce.This signature must be included in the add payment request’s encrypted data.

`completion`  

A completion handler that the system calls for the data needed to add a card to Apple Pay. This handler takes the following parameter:

`request`  
A PKAddPaymentPassRequestConfiguration object that contains the card data the system needs to add a card to Apple Pay.

