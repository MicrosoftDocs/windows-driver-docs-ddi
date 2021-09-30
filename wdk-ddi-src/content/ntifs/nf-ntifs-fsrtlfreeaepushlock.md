---
UID: NF:ntifs.FsRtlFreeAePushLock
tech.root: ifsk
title: FsRtlFreeAePushLock
ms.date: 09/29/2021
targetos: Windows
description: Learn more about the FsRtlFreeAePushLock macro.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: <= APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 20H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - ntifs.h
api_name:
 - FsRtlFreeAePushLock
f1_keywords:
 - FsRtlFreeAePushLock
 - ntifs/FsRtlFreeAePushLock
dev_langs:
 - c++
---

## -description

**FsRtlFreeAePushLock** deallocates an auto-expand push lock.

## -parameters

### -param AePushLock

[in] Pointer to an auto-expand push lock that was allocated by [**FsRtlAllocateAePushLock**](nf-ntifs-fsrtlallocateaepushlock.md).

## -remarks

See [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) for more information about auto-expand push locks.

## -see-also

[**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md)

[**FsRtlAllocateAePushLock**](nf-ntifs-fsrtlallocateaepushlock.md)
