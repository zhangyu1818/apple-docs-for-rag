

- Security
-  kSecCodeInfoDesignatedRequirement 

Global Variable

# kSecCodeInfoDesignatedRequirement

A keys whose value is the designated requirement of the code.

Mac Catalyst 13.0+macOS 10.0+

``` source
let kSecCodeInfoDesignatedRequirement: CFString
```

## Discussion

The value is a SecRequirement object. If this object is identical to the one returned by the kSecCodeInfoImplicitDesignatedRequirement key, then there is no explicit designated requirement and the designated requirement in use was generated by the system.

Specify the kSecCSRequirementInformation flag when calling the SecCodeCopySigningInformation(_:_:_:) function to get this information.

