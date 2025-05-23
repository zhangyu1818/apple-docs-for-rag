

- DeviceCheck
-  Attestation Object Validation Guide 

Article

# Attestation Object Validation Guide

Use this guide to validate your implementation of verifying the attestation object verification process.

### Example setup

Consider we have an example iOS Application with the following properties:

```
appIDPrefix = "0352187391" (teamID)
bundleID = "com.apple.example_app_attest"
serverChallenge = "test_server_challenge"
```

After calling generateKey, this example produces the following `keyId`:

```
"bSrEhF8TIzIvWSPwvZ0i2+UOBre4ASH84rK15m6emNY="
```

Note

The `keyId` from the generateKey API is already in Base64 encoded format.

After calling attestKey, this example produces the following `attestationObject`, as a Base64 encoded string:

```
"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"
```

You may use this guide as a reference to cross-check your attestation object validation operations against this sample attestation object, to ensure you are producing the correct results at each step, in your use case.

### Walking through the validation steps

1.  Verify that the `x5c` array contains the intermediate and leaf certificates for App Attest, starting from the credential certificate in the first data buffer in the array (`credcert`). Verify the validity of the certificates using Apple’s App Attest root certificate.

Expected leaf certificate, as a Base64 encoded string:

```
"MIIDsjCCAzmgAwIBAgIGAY7x/U1KMAoGCCqGSM49BAMCME8xIzAhBgNVBAMMGkFwcGxlIEFwcCBBdHRlc3RhdGlvbiBDQSAxMRMwEQYDVQQKDApBcHBsZSBJbmMuMRMwEQYDVQQIDApDYWxpZm9ybmlhMB4XDTI0MDQxNzE2MTQ1M1oXDTI0MDQyMDE2MTQ1M1owgZExSTBHBgNVBAMMQDZkMmFjNDg0NWYxMzIzMzIyZjU5MjNmMGJkOWQyMmRiZTUwZTA2YjdiODAxMjFmY2UyYjJiNWU2NmU5ZTk4ZDYxGjAYBgNVBAsMEUFBQSBDZXJ0aWZpY2F0aW9uMRMwEQYDVQQKDApBcHBsZSBJbmMuMRMwEQYDVQQIDApDYWxpZm9ybmlhMFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEjC4Mq2+SI5cOf1q26S/XpNbWIaYOVIZEvxl2TvHvhTYR9sK2u1Oyu6LTRoGX5L6rLDbKwOTiT0HzUTLJR15cJKOCAbwwggG4MAwGA1UdEwEB/wQCMAAwDgYDVR0PAQH/BAQDAgTwMIGIBgkqhkiG92NkCAUEezB5pAMCAQq/iTADAgEBv4kxAwIBAL+JMgMCAQG/iTMDAgEBv4k0KQQnMDM1MjE4NzM5MS5jb20uYXBwbGUuZXhhbXBsZV9hcHBfYXR0ZXN0pQYEBHNrcyC/iTYDAgEFv4k3AwIBAL+JOQMCAQC/iToDAgEAv4k7AwIBADCB1wYJKoZIhvdjZAgHBIHJMIHGv4p4BgQEMTguML+IUAcCBQD/////v4p7CQQHMjJBMjQ0Yr+KfAYEBDE4LjC/in0GBAQxOC4wv4p+AwIBAL+KfwMCAQC/iwADAgEAv4sBAwIBAL+LAgMCAQC/iwMDAgEAv4sEAwIBAb+LBQMCAQC/iwoQBA4yMi4xLjI0NC4wLjIsML+LCxAEDjIyLjEuMjQ0LjAuMiwwv4sMEAQOMjIuMS4yNDQuMC4yLDC/iAIKBAhpcGhvbmVvc7+IBQoECEludGVybmFsMDMGCSqGSIb3Y2QIAgQmMCShIgQg+20WKnF+yrF3iQBQb6lNZ+4MHcPUWxLN3oG+/Fblt+swCgYIKoZIzj0EAwIDZwAwZAIwIk4vHloC64CyG7xk6mEC2wNk4hFv+CryBxCTirG4ZOdRgu0CrvFuj3zQEmtLDUe2AjACi2YebCyyzhd8AwH1hvLgIrpmMj2AJiy0is9Z5OLDYkz9BNUX0IBWGJlewqdr2iU="
```

Expected intermediate certificate, as a Base64 encoded string:

```
"MIICQzCCAcigAwIBAgIQCbrF4bxAGtnUU5W8OBoIVDAKBggqhkjOPQQDAzBSMSYwJAYDVQQDDB1BcHBsZSBBcHAgQXR0ZXN0YXRpb24gUm9vdCBDQTETMBEGA1UECgwKQXBwbGUgSW5jLjETMBEGA1UECAwKQ2FsaWZvcm5pYTAeFw0yMDAzMTgxODM5NTVaFw0zMDAzMTMwMDAwMDBaME8xIzAhBgNVBAMMGkFwcGxlIEFwcCBBdHRlc3RhdGlvbiBDQSAxMRMwEQYDVQQKDApBcHBsZSBJbmMuMRMwEQYDVQQIDApDYWxpZm9ybmlhMHYwEAYHKoZIzj0CAQYFK4EEACIDYgAErls3oHdNebI1j0Dn0fImJvHCX+8XgC3qs4JqWYdP+NKtFSV4mqJmBBkSSLY8uWcGnpjTY71eNw+/oI4ynoBzqYXndG6jWaL2bynbMq9FXiEWWNVnr54mfrJhTcIaZs6Zo2YwZDASBgNVHRMBAf8ECDAGAQH/AgEAMB8GA1UdIwQYMBaAFKyREFMzvb5oQf+nDKnl+url5YqhMB0GA1UdDgQWBBQ+410cBBmpybQx+IR01uHhV3LjmzAOBgNVHQ8BAf8EBAMCAQYwCgYIKoZIzj0EAwMDaQAwZgIxALu+iI1zjQUCz7z9Zm0JV1A1vNaHLD+EMEkmKe3R+RToeZkcmui1rvjTqFQz97YNBgIxAKs47dDMge0ApFLDukT5k2NlU/7MKX8utN+fXr5aSsq2mVxLgg35BDhveAe7WJQ5tw=="
```

2.  Create `clientDataHash` as the SHA256 hash of the one-time challenge your server sends to your app before performing the attestation, and append that hash to the end of the authenticator data (`authData` from the decoded object).

Expected clientDataHash, as a Base64 encoded string:

```
"FVhAM8lQuf6dUUziohGjJtcaprEBSrTG+i+9qdmqGKZAAAAAAGFwcGF0dGVzdAAAAAAAAAAAIG0qxIRfEyMyL1kj8L2dItvlDga3uAEh/OKyteZunpjWpQECAyYgASFYIIwuDKtvkiOXDn9atukv16TW1iGmDlSGRL8Zdk7x74U2IlggEfbCtrtTsrui00aBl+S+qyw2ysDk4k9B81EyyUdeXCR0ZXN0X3NlcnZlcl9jaGFsbGVuZ2U="
```

3.  Generate a new SHA256 hash of the composite item to create `nonce`.

Expected nonce, as Base64 encoded string:

```
"+20WKnF+yrF3iQBQb6lNZ+4MHcPUWxLN3oG+/Fblt+s="
```

4.  Obtain the value of the `credCert` extension with OID `1.2.840.113635.100.8.2`, which is a DER-encoded ASN.1 sequence. Decode the sequence and extract the single octet string that it contains. Verify that the string equals `nonce`.

Expected octet string from `credCert`, as a Base64 encoded string:

```
"+20WKnF+yrF3iQBQb6lNZ+4MHcPUWxLN3oG+/Fblt+s="
```

5.  Create the SHA256 hash of the public key in `credCert` with X9.62 uncompressed point format, and verify that it matches the key identifier from your app.

Expected public key SHA256 hash from `credCert`, as a Base64 encoded string:

```
"bSrEhF8TIzIvWSPwvZ0i2+UOBre4ASH84rK15m6emNY="
```

6.  Compute the SHA256 hash of your app’s App ID, and verify that it’s the same as the authenticator data’s `RP ID` hash.

Expected SHA256 hash of App ID, as a Base64 encoded string:

```
"FVhAM8lQuf6dUUziohGjJtcaprEBSrTG+i+9qdmqGKY="
```

Expected hash of `RP_ID` from the authenticator data field:

```
"FVhAM8lQuf6dUUziohGjJtcaprEBSrTG+i+9qdmqGKY="
```

7.  Verify that the authenticator data’s `counter` field equals `0`.

Expected counter field:

```
0
```

Note

The `counter` is incremented on each subsequent call to generateAssertion, following the call to attestKey.

8.  Verify that the authenticator data’s `aaguid` field is either `appattestdevelop` if operating in the development environment, or `appattest` followed by seven `0x00` bytes if operating in the production environment.

Expected `aaguid` field for production:

```
"\x61\x70\x70\x61\x74\x74\x65\x73\x74\x00\x00\x00\x00\x00\x00\x00"
```

9.  Verify that the authenticator data’s `credentialId` field is the same as the key identifier.

Expected `credentialId`:

```
"bSrEhF8TIzIvWSPwvZ0i2+UOBre4ASH84rK15m6emNY="
```

