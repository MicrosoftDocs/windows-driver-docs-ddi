---
UID: NF:dbgmodel.IDebugHostMemory5.ReadIntrinsics
tech.root: debugger
title: IDebugHostMemory5::ReadIntrinsics
ms.date: 02/24/2025
targetos: Windows
description: The ReadIntrinsics method reads one or more intrinsic values from the target's address space defined by the given context and location. 
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
 - IDebugHostMemory5::ReadIntrinsics
f1_keywords:
 - IDebugHostMemory5::ReadIntrinsics
 - dbgmodel/IDebugHostMemory5::ReadIntrinsics
dev_langs:
 - c++
helpviewer_keywords:
 - ReadIntrinsics
---

## -description

The ReadIntrinsics method reads one or more intrinsic values from the target's address space defined by the given context and location. The number of intrinsics successfully read is returned in the intrinsicsRead on success.

The method allows reading of different types of intrinsics which are indicated by the 'vt' parameter. These types can be:

- VT_I1 - VT_I8: Signed integers
- VT_UI1 - VT_UI1: Unsigned integers
- VT_R4 - VT_R8: Standard floating point (single/double precision) values

## -parameters

### -param context

The currently active context.

### -param location

The location in the target's address space from where intrinsic values will be read.

### -param vt

Specifies the type of intrinsic values to read.

### -param count

Specifies the number of intrinsic values to read.

### -param vals

A pointer to the storage location where the read intrinsic values will be stored.

### -param intrinsicsRead

Returns the number of intrinsics successfully read.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory5 interface](nn-dbgmodel-idebughostmemory5.md)