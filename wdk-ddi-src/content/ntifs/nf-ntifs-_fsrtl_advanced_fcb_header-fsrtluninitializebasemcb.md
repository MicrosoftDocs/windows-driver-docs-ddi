---
UID: NF:ntifs.FsRtlUninitializeBaseMcb
title: FsRtlUninitializeBaseMcb function (ntifs.h)
description: The FsRtlUninitializeBaseMcb function uninitializes a map control block (MCB) structure.  After calling this routine the input Mcb structure must be re-initialized before being used again.
tech.root: ifsk
ms.date: 10/19/2018
keywords: ["FsRtlUninitializeBaseMcb function"]
ms.keywords: FsRtlUninitializeBaseMcb
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - FsRtlUninitializeBaseMcb
 - ntifs/FsRtlUninitializeBaseMcb
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlUninitializeBaseMcb
dev_langs:
 - c++
---

# FsRtlUninitializeBaseMcb function


## -description

The **FsRtlUninitializeBaseMcb** function uninitializes a map control block (MCB) structure.  After calling this routine the input Mcb structure must be re-initialized before being used again.

## -parameters

### -param Mcb

Supplies a pointer to the Mcb structure to uninitialize.

## -remarks

## -see-also

[**FsRtlInitializeLargeMcb**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb.md)
