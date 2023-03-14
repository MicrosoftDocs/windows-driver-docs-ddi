---
UID: NC:ntifs.PCOMPLETE_LOCK_IRP_ROUTINE
tech.root: ifsk
title: PCOMPLETE_LOCK_IRP_ROUTINE
ms.date: 03/13/2023
targetos: Windows
description: Learn more about the PCOMPLETE_LOCK_IRP_ROUTINE callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: APC_LEVEL
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
 - LibDef
api_location:
 - ntifs.h
api_name:
 - PCOMPLETE_LOCK_IRP_ROUTINE
f1_keywords:
 - PCOMPLETE_LOCK_IRP_ROUTINE
 - ntifs/PCOMPLETE_LOCK_IRP_ROUTINE
dev_langs:
 - c++
helpviewer_keywords:
 - PCOMPLETE_LOCK_IRP_ROUTINE
---

## -description

A file system filter driver (legacy filter) can register a PCOMPLETE_LOCK_IRP_ROUTINE-typed routine as the filter's *CompleteLockIrpRoutine* callback.

## -parameters

### -param Context

[in] Context pointer that was passed to [**FsRtlProcessFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock.md).

### -param Irp

[in] IRP for the file lock [**IRP_MJ_LOCK_CONTROL**](irp-mj-lock-control.md) request that is being completed. The lock request type will be one of the following:

* IRP_MN_LOCK
* IRP_MN_UNLOCK_ALL
* IRP_MN_UNLOCK_ALL_BY_KEY
* IRP_MN_UNLOCK_SINGLE

## -returns

This routine returns STATUS_SUCCESS or an appropriate NTSTATUS value. If it returns an NTSTATUS value that is not a success code, the file lock is removed from the file.

## -remarks

A file system filter driver (legacy filter) can optionally specify a PCOMPLETE_LOCK_IRP_ROUTINE-typed routine as the legacy filter's *CompleteLockIrpRoutine* routine for a byte-range file lock.

To specify this routine, a legacy filter passes a pointer to the routine as the *CompleteLockIrpRoutine* parameter for [**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md) or [**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md).

If the legacy filter specifies a *CompleteLockIrpRoutine* routine for a file lock, the system calls this routine when completing an [**IRP_MJ_LOCK_CONTROL**](irp-mj-lock-control.md) operation for the file lock.

## -see-also

[**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md)

[**FsRtlCheckLockForReadAccess**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforreadaccess.md)

[**FsRtlCheckLockForWriteAccess**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforwriteaccess.md)

[**FsRtlFreeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfreefilelock.md)

[**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md)

[**FsRtlProcessFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock.md)

[**FsRtlUninitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md)

[**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)

[**PUNLOCK_ROUTINE**](/windows-hardware/drivers/ifs/punlock-routine)
