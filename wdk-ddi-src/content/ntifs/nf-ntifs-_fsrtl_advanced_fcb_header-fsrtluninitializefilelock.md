---
UID: NF:ntifs.FsRtlUninitializeFileLock
title: FsRtlUninitializeFileLock function (ntifs.h)
description: The FsRtlUninitializeFileLock routine uninitializes a FILE_LOCK structure.
old-location: ifsk\fsrtluninitializefilelock.htm
tech.root: ifsk
ms.assetid: e92763e2-a15a-41cd-9f69-ec759b254929
ms.date: 04/16/2018
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

The <b>FsRtlUninitializeFileLock</b> routine uninitializes a FILE_LOCK structure.

## -parameters

### -param FileLock 

[in]
Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>.

## -remarks

<b>FsRtlUninitializeFileLock</b> uninitializes an initialized FILE_LOCK structure and completes any outstanding <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-lock-control">IRP_MJ_LOCK_CONTROL</a> requests. The uninitialized FILE_LOCK structure can be initialized for reuse by a subsequent call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>.

<b>FsRtlUninitializeFileLock</b> can be used to uninitialize a FILE_LOCK structure that was initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>. Do not use <b>FsRtlUninitializeFileLock</b> for such a FILE_LOCK structure unless the structure is to be initialized for reuse. It is a programming error to call <b>FsRtlFreeFileLock</b> for an uninitialized FILE_LOCK structure.

Minifilters must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltuninitializefilelock">FltUninitializeFileLock</a> instead of <b>FsRtlUninitializeFileLock</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltuninitializefilelock">FltUninitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-lock-control">IRP_MJ_LOCK_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/pcomplete-lock-irp-routine">PCOMPLETE_LOCK_IRP_ROUTINE</a>

