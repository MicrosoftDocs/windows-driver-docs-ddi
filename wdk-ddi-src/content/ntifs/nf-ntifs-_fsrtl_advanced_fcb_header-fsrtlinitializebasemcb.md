---
UID: NF:ntifs.FsRtlInitializeBaseMcb
title: FsRtlInitializeBaseMcb function (ntifs.h)
description: FsRtlInitializeBaseMcb initializes a new map control block (MCB) structure.
ms.assetid: 78f5f4e1-0756-4071-931c-3d8503ff1dab
tech.root: ifsk
ms.date: 10/19/2018
keywords: ["FsRtlInitializeBaseMcb function"]
f1_keywords:
 - "ntifs/FsRtlInitializeBaseMcb"
 - "FsRtlInitializeBaseMcb"
ms.keywords: FsRtlInitializeBaseMcb
req.header: ntifs.h
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- FsRtlInitializeBaseMcb
targetos: Windows
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlInitializeBaseMcb function

## -description

**FsRtlInitializeBaseMcb** initializes a new map control block (MCB) structure.

## -parameters

### -param Mcb

Pointer to the MCB structure to initialize.

### -param PoolType

Specifies the pool type to use when allocating additional internal MCB memory.

## -remarks

The caller supplies the memory for the MCB structure.  A call to **FsRtlInitializeBaseMcb** must precede all other calls that set/query the MCB structure.

If pool is not available, this routine will raise a status value indicating insufficient resources.

## -see-also

[FsRtlInitializeBaseMcbEx function](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializebasemcbex.md)
