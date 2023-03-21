---
UID: NF:ntifs.FsRtlInitializeFileLock
title: FsRtlInitializeFileLock function (ntifs.h)
description: The FsRtlInitializeFileLock routine initializes a FILE_LOCK structure.
old-location: ifsk\fsrtlinitializefilelock.htm
tech.root: ifsk
ms.date: 03/20/2023
keywords: ["FsRtlInitializeFileLock function"]
ms.keywords: FsRtlInitializeFileLock, FsRtlInitializeFileLock routine [Installable File System Drivers], fsrtlref_227dc998-43e4-427b-afe5-6d26ff5d1c36.xml, ifsk.fsrtlinitializefilelock, ntifs/FsRtlInitializeFileLock
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlInitializeFileLock
 - ntifs/FsRtlInitializeFileLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlInitializeFileLock
dev_langs:
 - c++
---

# FsRtlInitializeFileLock function

## -description

The **FsRtlInitializeFileLock** routine initializes a FILE_LOCK structure.

## -parameters

### -param FileLock [in]

Pointer to an uninitialized [**FILE_LOCK**](ns-ntifs-file_lock.md) structure.

### -param CompleteLockIrpRoutine [in, optional]

Pointer to a [**PCOMPLETE_LOCK_IRP_ROUTINE**](nc-ntifs-pcomplete_lock_irp_routine.md)-typed callback routine to be called when an [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) request is completed. This parameter is optional and can be NULL.

### -param UnlockRoutine [in, optional]

Pointer to a [**PUNLOCK_ROUTINE**](nc-ntifs-punlock_routine.md)-typed callback routine to be called when the byte range is unlocked. This parameter is optional and can be NULL.

## -remarks

**FsRtlInitializeFileLock** initializes an uninitialized FILE_LOCK structure.

It is a programming error to call **FsRtlInitializeFileLock** for a FILE_LOCK structure that has already been initialized by **FsRtlInitializeFileLock** or [**FltAllocateFileLock**](../fltkernel/nf-fltkernel-fltallocatefilelock.md), unless the structure has been uninitialized by a subsequent call to [**FsRtlUninitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md).

Once initialized, the FILE_LOCK structure can be used to lock a byte range in a file by calling [**FsRtlProcessFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock.md) or[**FsRtlFastLock**](nf-ntifs-fsrtlfastlock.md). **FsRtlProcessFileLock** processes lock IRPs. **FsRtlFastLock** performs non-IRP locking.

When the **FILE_LOCK** structure is no longer needed, it can be uninitialized by calling [**FsRtlUninitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md). The uninitialized FILE_LOCK structure can then be initialized for reuse by calling **FsRtlInitializeFileLock**.

Minifilters must call [**FltInitializeFileLock**](../fltkernel/nf-fltkernel-fltinitializefilelock.md) instead of **FsRtlInitializeFileLock**.

## -see-also

[**FILE_LOCK**](ns-ntifs-file_lock.md)

[**FltInitializeFileLock**](../fltkernel/nf-fltkernel-fltinitializefilelock.md)

[**FltAllocateFileLock**](../fltkernel/nf-fltkernel-fltallocatefilelock.md)

[**FsRtlAreThereCurrentFileLocks**](nf-ntifs-fsrtlaretherecurrentfilelocks.md)

[**FsRtlFastLock**](nf-ntifs-fsrtlfastlock.md)

[**FsRtlProcessFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock.md)

[**FsRtlUninitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md)

[**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)

[**IoCompleteRequest**](../wdm/nf-wdm-iocompleterequest.md)

[**PCOMPLETE_LOCK_IRP_ROUTINE**](nc-ntifs-pcomplete_lock_irp_routine.md)

[**PUNLOCK_ROUTINE**](nc-ntifs-punlock_routine.md)
