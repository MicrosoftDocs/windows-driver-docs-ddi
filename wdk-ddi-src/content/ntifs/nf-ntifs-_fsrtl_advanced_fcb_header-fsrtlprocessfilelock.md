---
UID: NF:ntifs.FsRtlProcessFileLock
title: FsRtlProcessFileLock function (ntifs.h)
description: The FsRtlProcessFileLock routine processes and completes an IRP for a file lock operation.
old-location: ifsk\fsrtlprocessfilelock.htm
tech.root: ifsk
ms.date: 09/10/2021
keywords: ["FsRtlProcessFileLock function"]
ms.keywords: FsRtlProcessFileLock, FsRtlProcessFileLock routine [Installable File System Drivers], fsrtlref_93a3a663-fe0b-45c2-ab32-af4fe94b9697.xml, ifsk.fsrtlprocessfilelock, ntifs/FsRtlProcessFileLock
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
 - FsRtlProcessFileLock
 - ntifs/FsRtlProcessFileLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlProcessFileLock
dev_langs:
 - c++
---

# FsRtlProcessFileLock function

## -description

The **FsRtlProcessFileLock** routine processes and completes an IRP for a file lock operation.

## -parameters

### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to [**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md) or [**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md).

### -param Irp [in]

Pointer to the IRP. Must be an IRP for a file-lock operation.

### -param Context [in, optional]

Optional context pointer to be used when completing IRPs.

## -returns

**FsRtlProcessFileLock** returns STATUS_SUCCESS on success; otherwise it returns an appropriate error status code.

## -remarks

**FsRtlProcessFileLock** performs the specified lock operation on behalf of the process associated with thread that originally requested the operation.

On Microsoft Windows XP and later, this is the process to which the thread is currently attached.

On Microsoft Windows 2000 and earlier, it is the process that created the thread.

Callers of **FsRtlProcessFileLock** relinquish control of the input IRP.

Minifilters must call [**FltProcessFileLock**](../fltkernel/nf-fltkernel-fltprocessfilelock.md) instead of **FsRtlProcessFileLock**.

## -see-also

[**FltProcessFileLock**](../fltkernel/nf-fltkernel-fltprocessfilelock.md)

[**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md)

[**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md)

[**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)
