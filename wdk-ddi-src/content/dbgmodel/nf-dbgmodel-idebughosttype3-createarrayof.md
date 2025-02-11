---
UID: NF:dbgmodel.IDebugHostType3.CreateArrayOf
tech.root: debugger
title: IDebugHostType3::CreateArrayOf
ms.date: 01/29/2025
targetos: Windows
description: The CreateArrayOf method, when called on a type, gets a new IDebugHostType that is an array of the type with specified array dimensions.
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
 - IDebugHostType3::CreateArrayOf
f1_keywords:
 - IDebugHostType3::CreateArrayOf
 - dbgmodel/IDebugHostType3::CreateArrayOf
dev_langs:
 - c++
helpviewer_keywords:
 - CreateArrayOf
---

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)

