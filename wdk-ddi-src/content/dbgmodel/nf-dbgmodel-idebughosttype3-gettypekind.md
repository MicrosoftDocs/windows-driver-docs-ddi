---
UID: NF:dbgmodel.IDebugHostType3.GetTypeKind
tech.root: debugger
title: IDebugHostType3::GetTypeKind
ms.date: 01/26/2025
targetos: Windows
description: The GetTypeKind method, when called on a type, gets the kind of type specified by the TypeKind enumeration.
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
 - IDebugHostType3::GetTypeKind
f1_keywords:
 - IDebugHostType3::GetTypeKind
 - dbgmodel/IDebugHostType3::GetTypeKind
dev_langs:
 - c++
helpviewer_keywords:
 - GetTypeKind
---

## -description

The GetTypeKind method returns what kind of type (pointer, array, intrinsic, etc...) the symbol refers to.

## -parameters

### -param kind

The kind of type the symbol refers to will be returned here (as a member of the [TypeKind enumeration](ne-dbgmodel-typekind)).

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType2> spType; /* get a type (see FindTypeByName) */

TypeKind tk;
if (SUCCEEDED(spType->GetTypeKind(&tk)))
{
    // tk is the kind of type
    //    TypePointer: it's a pointer
    //    TypeArray:   it's an array
    //    etc...
}

```

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)