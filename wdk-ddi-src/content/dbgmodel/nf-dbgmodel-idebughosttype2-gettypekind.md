---
UID: NF:dbgmodel.IDebugHostType2.GetTypeKind
title: IDebugHostType2::GetTypeKind (dbgmodel.h)
description: "The IDebugHostType2::GetTypeKind method, when called on a type, gets the kind of type specified by the TypeKind enumeration."
ms.date: 09/20/2018
keywords: ["IDebugHostType2::GetTypeKind"]
ms.keywords: IDebugHostType2::GetTypeKind, GetTypeKind, IDebugHostType2.GetTypeKind, IDebugHostType2::GetTypeKind, IDebugHostType2.GetTypeKind
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
 - IDebugHostType2::GetTypeKind
 - dbgmodel/IDebugHostType2::GetTypeKind
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2::GetTypeKind
---

# IDebugHostType2::GetTypeKind


## -description

The GetTypeKind method returns what kind of type (pointer, array, intrinsic, etc...) the symbol refers to.

## -parameters

### -param kind

The kind of type the symbol refers to will be returned here (as a member of the TypeKind enumeration).

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

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

