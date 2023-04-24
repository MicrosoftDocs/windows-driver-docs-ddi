---
UID: NF:ntifs.FsRtlUninitializeFileLock
title: FsRtlUninitializeFileLock function (ntifs.h)
description: The FsRtlUninitializeFileLock routine uninitializes a FILE_LOCK structure.
old-location: ifsk\fsrtluninitializefilelock.htm
tech.root: ifsk
ms.date: 03/20/2023
keywords: ["FsRtlUninitializeFileLock function"]
ms.keywords: FsRtlUninitializeFileLock, FsRtlUninitializeFileLock routine [Installable File System Drivers], fsrtlref_d78c3eae-751c-4440-8915-455454886201.xml, ifsk.fsrtluninitializefilelock, ntifs/FsRtlUninitializeFileLock
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
f1_keywords:
 - FsRtlUninitializeFileLock
 - ntifs/FsRtlUninitializeFileLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlUninitializeFileLock
---

# FsRtlUninitializeFileLock function

## -description

The **FsRtlUninitializeFileLock** routine uninitializes a [**FILE_LOCK**](ns-ntifs-file_lock.md) structure.

## -parameters

### -param FileLock [in]

Pointer to the [**FILE_LOCK**](ns-ntifs-file_lock.md) structure for the file. This structure must have been initialized by a previous call to [**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md) or [**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md).

## -remarks

**FsRtlUninitializeFileLock** uninitializes an initialized FILE_LOCK structure and completes any outstanding [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) requests. The uninitialized FILE_LOCK structure can be initialized for reuse by a subsequent call to [**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md).

**FsRtlUninitializeFileLock** can be used to uninitialize a FILE_LOCK structure that was initialized by a previous call to [**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md) or [**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md). Do not use **FsRtlUninitializeFileLock** for such a FILE_LOCK structure unless the structure is to be initialized for reuse. It is a programming error to call **FsRtlFreeFileLock** for an uninitialized FILE_LOCK structure.

Minifilters must call [**FltUninitializeFileLock**](../fltkernel/nf-fltkernel-fltuninitializefilelock.md) instead of **FsRtlIninitializeFileLock**.

## -see-also

[**FILE_LOCK**](ns-ntifs-file_lock.md)

[**FltUninitializeFileLock**](../fltkernel/nf-fltkernel-fltuninitializefilelock.md)

[**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md)

[**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md)

[**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)

[**PCOMPLETE_LOCK_IRP_ROUTINE**](nc-ntifs-pcomplete_lock_irp_routine.md)
