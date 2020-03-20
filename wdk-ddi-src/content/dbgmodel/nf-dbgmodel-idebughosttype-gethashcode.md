---
UID: NF:dbgmodel.IDebugHostType.GetHashCode
title: IDebugHostType::GetHashCode (dbgmodel.h)
description: The GetHashCode method returns a 32-bit hash code for the type. 
ms.assetid: e99f9667-bcb2-4209-9581-bd6c55ba9426
ms.date: 08/22/2018
keywords: ["IDebugHostType::GetHashCode"]
f1_keywords:
 - "dbgmodel/IDebugHostType.GetHashCode"
ms.keywords: IDebugHostType::GetHashCode, GetHashCode, IDebugHostType.GetHashCode, IDebugHostType::GetHashCode, IDebugHostType.GetHashCode
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
- IDebugHostType.GetHashCode
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType::GetHashCode


## -description

The GetHashCode method returns a 32-bit hash code for the type. With the exception of a global match (e.g.: a type signature equivalent to * which matches everything if permitted by the host), any type instance which can match a particular type signature must return the same hash code. 

This method is used in conjunction with type signatures in order to match type signatures to type instances. 


## -parameters

### -param hashCode
A 32-bit hash code for the type instance. Every type which is capable of matching another type via a non-global match type signature will return the same hash code here. The debug host must guarantee such synchronization between its type signature methods and this method.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type (see FindTypeByName) */

ULONG typeHash;
if (SUCCEEDED(spType->GetHashCode(&typeHash)))
{
    // typeHash contains a 32-bit hash code.  The hash must be identical for 
    // every type which can match a type signature (unless the signature 
    // is a total wildcard).
}
```

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
