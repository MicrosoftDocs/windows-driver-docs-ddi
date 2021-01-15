---
UID: NF:dbgmodel.IDebugHostType2.CreateArrayOf
title: IDebugHostType2::CreateArrayOf (dbgmodel.h)
description: For any given type, this returns a new IDebugHostType which is an array of this type.
ms.date: 09/20/2018
keywords: ["IDebugHostType2::CreateArrayOf"]
ms.keywords: IDebugHostType2::CreateArrayOf, CreateArrayOf, IDebugHostType2.CreateArrayOf, IDebugHostType2::CreateArrayOf, IDebugHostType2.CreateArrayOf
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
 - IDebugHostType2::CreateArrayOf
 - dbgmodel/IDebugHostType2::CreateArrayOf
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2::CreateArrayOf
---

# IDebugHostType2::CreateArrayOf


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

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

