---
UID: NF:ntifs.FsRtlAllocateFileLock
title: FsRtlAllocateFileLock function (ntifs.h)
description: The FsRtlAllocateFileLock routine allocates and initializes a new FILE_LOCK structure.
tech.root: ifsk
ms.date: 03/20/2023
keywords: ["FsRtlAllocateFileLock function"]
ms.keywords: FsRtlAllocateFileLock, FsRtlAllocateFileLock routine [Installable File System Drivers], fsrtlref_cb42425d-add9-4c5b-bddc-54dc55448902.xml, ifsk.fsrtlallocatefilelock, ntifs/FsRtlAllocateFileLock
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
 - FsRtlAllocateFileLock
 - ntifs/FsRtlAllocateFileLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlAllocateFileLock
dev_langs:
 - c++
---

# FsRtlAllocateFileLock function

## -description

The **FsRtlAllocateFileLock** routine allocates and initializes a new FILE_LOCK structure.

## -parameters

### -param CompleteLockIrpRoutine [in, optional]

A pointer to a [**PCOMPLETE_LOCK_IRP_ROUTINE**](nc-ntifs-pcomplete_lock_irp_routine.md)-typed callback routine to be called when an [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) request is completed. This parameter is optional and can be NULL.

### -param UnlockRoutine [in, optional]

A pointer to a [**PUNLOCK_ROUTINE**](nc-ntifs-punlock_routine.md)-typed callback routine to be called when the byte range is unlocked. This parameter is optional and can be NULL.

## -returns

**FsRtlAllocateFileLock** returns a pointer to the newly allocated FILE_LOCK structure.

## -remarks

**FsRtlAllocateFileLock** allocates a new FILE_LOCK structure from paged pool and initializes it.

Minifilters should call [**FltAllocateFileLock**](../fltkernel/nf-fltkernel-fltallocatefilelock.md) instead of **FsRtlAllocateFileLock**.

## -see-also

[**FltAllocateFileLock**](../fltkernel/nf-fltkernel-fltallocatefilelock.md)

[**FsRtlAreThereCurrentFileLocks**](nf-ntifs-fsrtlaretherecurrentfilelocks.md)

[**FsRtlCheckLockForReadAccess**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforreadaccess.md)

[**FsRtlCheckLockForWriteAccess**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforwriteaccess.md)

[**FsRtlFastCheckLockForRead**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforread.md)

[**FsRtlFastCheckLockForWrite**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforwrite.md)

[**FsRtlFastLock**](nf-ntifs-fsrtlfastlock.md)

[**FsRtlFastUnlockAll**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlockall.md)

[**FsRtlFastUnlockAllByKey**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlockallbykey.md)

[**FsRtlFastUnlockSingle**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlocksingle.md)

[**FsRtlGetNextFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextfilelock.md)

[**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md)

[**FsRtlProcessFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock.md)

[**FsRtlUninitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md)

[**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)

[**PCOMPLETE_LOCK_IRP_ROUTINE**](nc-ntifs-pcomplete_lock_irp_routine.md)

[**PUNLOCK_ROUTINE**](nc-ntifs-punlock_routine.md)
