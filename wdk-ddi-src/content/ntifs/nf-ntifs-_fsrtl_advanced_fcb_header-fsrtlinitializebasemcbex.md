---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlInitializeBaseMcbEx
title: FsRtlInitializeBaseMcbEx function (ntifs.h)
description:
ms.assetid: ee7e2beb-fc03-4e76-8f68-b6fb9c6d26f8
ms.date: 10/19/2018
ms.topic: function
ms.keywords: FsRtlInitializeBaseMcbEx
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
-	FsRtlInitializeBaseMcbEx
product:
-	Windows
targetos: Windows

ms.custom: RS5
---

# FsRtlInitializeBaseMcbEx function


## -description

This routine initializes a new Mcb structure.  The caller must supply the memory for the Mcb structure.  This call must precede all other calls that set/query the Mcb structure.

If pool is not available this routine will raise a status value indicating insufficient resources or return false depending on the flags.

## -parameters

### -param Mcb
Contains a pointer to the Mcb structure to initialize.

### -param PoolType
Specifies the pool type to use when allocating additional internal Mcb memory.

### -param Flags
A bitmask of flags that specifies what action(s) to take when a Mcb mapping is empty. Contains one of the following values.

Flag|Value
---|---
MCB_FLAG_RAISE_ON_ALLOCATION_FAILURE|1

## -returns
This function returns a BOOLEAN and is TRUE if it is successfull initializing the Mcb structure.
## -remarks

## -see-also

[FsRtlInitializeBaseMcb function](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializebasemcb.md)
