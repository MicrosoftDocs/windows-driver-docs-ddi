---
UID: NF:dbgmodel.IDebugHostType2.GetHashCode
title: IDebugHostType2::GetHashCode (dbgmodel.h)
description: The GetHashCode method returns a 32-bit hash code for the type.
ms.date: 09/20/2018
keywords: ["IDebugHostType2::GetHashCode"]
ms.keywords: IDebugHostType2::GetHashCode, GetHashCode, IDebugHostType2.GetHashCode, IDebugHostType2::GetHashCode, IDebugHostType2.GetHashCode
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostType2::GetHashCode
 - dbgmodel/IDebugHostType2::GetHashCode
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2::GetHashCode
---

# IDebugHostType2::GetHashCode


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

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

