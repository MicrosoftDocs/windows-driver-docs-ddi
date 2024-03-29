---
UID: NF:dbgmodel.IDebugHostType.CreateArrayOf
title: IDebugHostType::CreateArrayOf (dbgmodel.h)
description: "The IDebugHostType::CreateArrayOf method, when called on a type, gets a new IDebugHostType that is an array of the type with specified array dimensions."
ms.date: 09/11/2018
keywords: ["IDebugHostType::CreateArrayOf"]
ms.keywords: IDebugHostType::CreateArrayOf, CreateArrayOf, IDebugHostType.CreateArrayOf, IDebugHostType::CreateArrayOf, IDebugHostType.CreateArrayOf
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
 - IDebugHostType::CreateArrayOf
 - dbgmodel/IDebugHostType::CreateArrayOf
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType::CreateArrayOf
---

# IDebugHostType::CreateArrayOf


## -description

For any given type, this returns a new [IDebugHostType](nn-dbgmodel-idebughosttype.md) which is an array of this type.
The dimensions of the array must be supplied via the "dimensions" and "pDimensions" arguments.

## -parameters

### -param dimensions

The number of dimensions of the array type to create.

### -param pDimensions

A pointer to an array of ArrayDimension structures describing the structure of each dimension of the array type to create.

### -param newType

The newly created array type will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)

