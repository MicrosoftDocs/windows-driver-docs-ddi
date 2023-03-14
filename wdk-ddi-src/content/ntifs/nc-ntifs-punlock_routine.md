---
UID: NC:ntifs.PUNLOCK_ROUTINE
tech.root: ifsk
title: PUNLOCK_ROUTINE
ms.date: 03/13/2023
targetos: Windows
description: Learn more about the PUNLOCK_ROUTINE callback routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: IRQL <= APC_LEVEL
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
 - PUNLOCK_ROUTINE
f1_keywords:
 - PUNLOCK_ROUTINE
 - ntifs/PUNLOCK_ROUTINE
dev_langs:
 - c++
helpviewer_keywords:
 - PUNLOCK_ROUTINE
---

## -description

A filter (legacy filter or minifilter) can register a PUNLOCK_ROUTINE-typed routine as the filter's *UnlockRoutine* callback routine for a [**FILE_LOCK**](ns-ntifs-file_lock.md) structure.

## -parameters

### -param Context

[in] Context pointer that was passed to [**FltProcessFileLock**](../fltkernel/nf-fltkernel-fltprocessfilelock.md) or [**FsRtlProcessFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock.md).

### -param FileLockInfo

Opaque pointer to the **FILE_LOCK_INFO** structure for the byte-range lock.

## -remarks

A filter (legacy filter or minifilter) can optionally specify a PUNLOCK_ROUTINE-typed routine as the filter's *UnlockRoutine* callback for a byte-range file lock.

If the filter specifies a *UnlockRoutine* routine for a FILE_LOCK structure, this routine is called when the lock is removed from a locked byte range in a file.

A minifilter specifies this routine by passing a pointer to the routine as the *UnlockRoutine* parameter for [**FltAllocateFileLock**](../fltkernel/nf-fltkernel-fltallocatefilelock).

A legacy filter specifies this routine by passing a pointer to the routine as the *UnlockRoutine* parameter for [**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md) or [**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md).

## -see-also

[**FltAllocateFileLock**](../fltkernel/nf-fltkernel-fltallocatefilelock.md)

[**FltCheckLockForReadAccess**](../fltkernel/nf-fltkernel-fltchecklockforreadaccess.md)

[**FltCheckLockForWriteAccess**](../fltkernel/nf-fltkernel-fltchecklockforwriteaccess.md)

[**FltFreeFileLock**](../fltkernel/nf-fltkernel-fltfreefilelock.md)

[**FltInitializeFileLock**](../fltkernel/nf-fltkernel-fltinitializefilelock.md)

[**FltProcessFileLock**](../fltkernel/nf-fltkernel-fltprocessfilelock.md)

[**FltUninitializeFileLock**](../fltkernel/nf-fltkernel-fltuninitializefilelock.md)

[**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md)

[**FsRtlCheckLockForReadAccess**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforreadaccess.md)

[**FsRtlCheckLockForWriteAccess**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforwriteaccess.md)

[**FsRtlFreeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfreefilelock.md)

[**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md)

[**FsRtlProcessFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock.md)

[**FsRtlUninitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md)

[**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)

[**PCOMPLETE_LOCK_IRP_ROUTINE**](nc-ntifs-pcomplete-lock-irp-routine.md)

[**PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE**](../fltkernel/nc-fltkernel-pflt_complete_lock_callback_data_routine.md)
