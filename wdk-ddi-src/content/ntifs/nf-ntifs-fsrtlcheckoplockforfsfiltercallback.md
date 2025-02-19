---
UID: NF:ntifs.FsRtlCheckOplockForFsFilterCallback
tech.root: ifsk
title: FsRtlCheckOplockForFsFilterCallback
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FsRtlCheckOplockForFsFilterCallback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: Less than or equal to APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlCheckOplockForFsFilterCallback
f1_keywords:
 - FsRtlCheckOplockForFsFilterCallback
 - ntifs/FsRtlCheckOplockForFsFilterCallback
dev_langs:
 - c++
helpviewer_keywords:
 - FsRtlCheckOplockForFsFilterCallback
---

## -description

A file system can call **FsRtlCheckOplockForFsFilterCallback** to break oplocks that are affected by file system filter operations.

### -param Oplock

[in] Pointer to the oplock structure for the file.

### -param CallbackData

[in] Pointer to the[**FS_FILTER_CALLBACK_DATA**](ns-ntifs-fs_filter_callback_data.md) structure describing the FS filter operation.

### -param Flags

[in] **OPLOCK_FLAG_*XXX*** values in the OPLOCK_FS_FILTER_FLAGS mask.

## -returns

**FsRtlCheckOplockForFsFilterCallback** returns TRUE if it can complete the operation on exiting this thread; otherwise, it returns FALSE.

## -remarks

FsFilter operations can't be pended and shouldn't be blocked, so this routine can only break oplocks asynchronously.

This routine handles the following operation. Passing any other FsFilter operations is an error.

* FS_FILTER_ACQUIRE_FOR_SECTION_SYNCHRONIZATION
