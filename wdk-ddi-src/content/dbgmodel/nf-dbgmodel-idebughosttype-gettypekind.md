---
UID: NF:dbgmodel.IDebugHostType.GetTypeKind
title: IDebugHostType::GetTypeKind (dbgmodel.h)
description: The GetTypeKind method returns what kind of type (pointer, array, intrinsic, etc...) the symbol refers to.
ms.date: 09/10/2018
keywords: ["IDebugHostType::GetTypeKind"]
ms.keywords: IDebugHostType::GetTypeKind, GetTypeKind, IDebugHostType.GetTypeKind, IDebugHostType::GetTypeKind, IDebugHostType.GetTypeKind
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
 - IDebugHostType::GetTypeKind
 - dbgmodel/IDebugHostType::GetTypeKind
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType::GetTypeKind
---

# IDebugHostType::GetTypeKind


## -description

The GetTypeKind method returns what kind of type (pointer, array, intrinsic, etc...) the symbol refers to. See the [TypeKind enumeration](ne-dbgmodel-typekind.md) for more information.

## -parameters

### -param kind

The kind of type the symbol refers to will be returned here (as a member of the TypeKind enumeration).

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type (see FindTypeByName) */

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

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)

