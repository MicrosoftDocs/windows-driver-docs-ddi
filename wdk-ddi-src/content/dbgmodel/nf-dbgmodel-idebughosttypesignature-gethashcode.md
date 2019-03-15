---
UID: NF:dbgmodel.IDebugHostTypeSignature.GetHashCode
title: IDebugHostTypeSignature::GetHashCode (dbgmodel.h)
description: The GetHashCode method returns a 32-bit hash code for the type signature. 
ms.assetid: ba7abda8-02c8-4487-b192-3e674679a278
ms.date: 09/10/2018
ms.topic: method
ms.keywords: IDebugHostTypeSignature::GetHashCode, GetHashCode, IDebugHostTypeSignature.GetHashCode, IDebugHostTypeSignature::GetHashCode, IDebugHostTypeSignature.GetHashCode
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostTypeSignature.GetHashCode
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostTypeSignature::GetHashCode


## -description

The GetHashCode method returns a 32-bit hash code for the type signature. The debug host guarantees that there is synchronization in implementation between the hash code returned for type instances and the hash code returned for type signatures. With the exception of a global match, if a type instance is capable of matching a type signature, both will have the same 32-bit hash code. This allows an initial rapid comparison and match between a type instance and a plethora of type signatures registered with the data model manager. 

## -parameters

### -param hashCode

A 32-bit hash code for the type signature is returned here. With the exception of a global match type signature, this hash code will be identical to the hash code of any type instance capable of matching this type signature.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks
**Sample Code**

```cpp
ComPtr<IDebugHostTypeSignature> spSig; /* create a type signature */

ULONG signatureHash;
if (SUCCEEDED(spSig->GetHashCode(&signatureHash)))
{
    // signatureHash contains a 32-bit hash code for the type signature.  
    // Unless the type signature is a complete wildcard, any type which CAN 
    // match this signature will have the same hash code returned 
    // from IDebugHostType::GetHashCode.
}
```

## -see-also

[IDebugHostTypeSignature interface](nn-dbgmodel-idebughosttypesignature.md)
