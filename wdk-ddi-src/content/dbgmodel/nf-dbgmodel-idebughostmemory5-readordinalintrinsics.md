---
UID: NF:dbgmodel.IDebugHostMemory5.ReadOrdinalIntrinsics
tech.root: debugger
title: IDebugHostMemory5::ReadOrdinalIntrinsics
ms.date: 02/24/2025
targetos: Windows
description: 
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
 - IDebugHostMemory5::ReadOrdinalIntrinsics
f1_keywords:
 - IDebugHostMemory5::ReadOrdinalIntrinsics
 - dbgmodel/IDebugHostMemory5::ReadOrdinalIntrinsics
dev_langs:
 - c++
helpviewer_keywords:
 - ReadOrdinalIntrinsics
---

## -description

The ReadOrdinalIntrinsics method reads one or more intrinsic values from the target's address space as defined by the given context and location. This method is similar to ReadIntrinsics(), but the type of intrinsic is specified by an ordinal size and an indication of whether the intrinsics are signed. This method supports 8-64 bit signed and unsigned ordinals.

## -parameters

### -param context

The context in effect.

### -param location

The location from where intrinsic values will be read

### -param ordinalSize

Specifies the size of the ordinal intrinsics to read.

### -param ordinalIsSigned

Specifies whether the ordinal intrinsics are signed or not.

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