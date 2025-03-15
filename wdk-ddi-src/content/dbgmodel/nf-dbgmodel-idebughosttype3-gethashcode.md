---
UID: NF:dbgmodel.IDebugHostType3.GetHashCode
tech.root: debugger
title: IDebugHostType3::GetHashCode
ms.date: 01/26/2025
targetos: Windows
description: The GetHashCode method, when called on a type, gets a 32-bit hash code for the type.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType3::GetHashCode
f1_keywords:
 - IDebugHostType3::GetHashCode
 - dbgmodel/IDebugHostType3::GetHashCode
dev_langs:
 - c++
helpviewer_keywords:
 - GetHashCode
---

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)