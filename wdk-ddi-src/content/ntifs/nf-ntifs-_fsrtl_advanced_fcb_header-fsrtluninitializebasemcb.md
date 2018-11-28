---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlUninitializeBaseMcb
title: FsRtlUninitializeBaseMcb function
author: windows-driver-content
description: The FsRtlUninitializeBaseMcb function uninitializes a map control block (MCB) structure.  After calling this routine the input Mcb structure must be re-initialized before being used again.
ms.assetid: 3c20cc02-add4-4ebb-92bf-1a50e6646439
ms.date: 10/19/2018
ms.topic: function
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
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtosKrnl.exe
api_name: 
-	FsRtlUninitializeBaseMcb
product:
-	Windows
targetos: Windows

ms.custom: RS5
---

# FsRtlUninitializeBaseMcb function


## -description
The **FsRtlUninitializeBaseMcb** function uninitializes a map control block (MCB) structure.  After calling this routine the input Mcb structure must be re-initialized before being used again.

## -parameters

### -param Mcb
Supplies a pointer to the Mcb structure to uninitialize.

## -returns
None.

## -remarks

## -see-also

[FsRtlInitializeLargeMcb function](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md)
