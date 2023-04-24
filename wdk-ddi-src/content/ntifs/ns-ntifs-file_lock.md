---
UID: NS:ntifs._FILE_LOCK
tech.root: ifsk
title: FILE_LOCK
ms.date: 03/13/2023
targetos: Windows
description: Learn more about the FILE_LOCK structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.typenames: FILE_LOCK
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_LOCK
 - FILE_LOCK
f1_keywords:
 - _FILE_LOCK
 - ntifs/_FILE_LOCK
 - FILE_LOCK
 - ntifs/FILE_LOCK
dev_langs:
 - c++
helpviewer_keywords:
 - _FILE_LOCK
---

## -description

This structure is reserved for system use. The operating system uses the opaque **FILE_LOCK** structure to support the locking of files.

## -struct-fields

### -field CompleteLockIrpRoutine

Reserved for system use.

### -field UnlockRoutine

Reserved for system use.

### -field FastIoIsQuestionable

Reserved for system use.

### -field SpareC[3]

Reserved for system use.

### -field LockInformation

Reserved for system use.

### -field LastReturnedLockInfo

Reserved for system use.

### -field LastReturnedLock

Reserved for system use.

### -field LockRequestsInProgress

Reserved for system use.

## -see-also

[**PCOMPLETE_LOCK_IRP_ROUTINE**](nc-ntifs-pcomplete_lock_irp_routine.md)
