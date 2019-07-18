---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlInitializeBaseMcb
title: FsRtlInitializeBaseMcb function (ntifs.h)
description: This routine initializes a new Mcb structure.  The caller must supply the memory for the Mcb structure.  This call must precede all other calls that set/query the Mcb structure.
ms.assetid: 78f5f4e1-0756-4071-931c-3d8503ff1dab
ms.date: 10/19/2018
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlInitializeBaseMcb"
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
product:
- Windows
targetos: Windows

ms.custom: RS5
---

# FsRtlInitializeBaseMcb function


## -description
This routine initializes a new map control block (MCB) structure. The caller must supply the memory for the Mcb structure. This call must precede all other calls that set/query the Mcb structure.

If pool is not available this routine will raise a status value indicating insufficient resources.

## -parameters

### -param Mcb

Contains a pointer to the Mcb structure to initialize.

### -param PoolType
Specifies the pool type to use when allocating additional internal Mcb memory.

## -returns

None.

## -remarks

## -see-also
[FsRtlInitializeBaseMcbEx function](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializebasemcbex.md)
