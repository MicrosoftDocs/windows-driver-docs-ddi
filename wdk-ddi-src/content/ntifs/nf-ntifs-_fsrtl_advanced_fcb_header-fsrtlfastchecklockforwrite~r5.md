---
UID: NF:ntifs.FsRtlFastCheckLockForWrite~r5
title: FsRtlFastCheckLockForWrite function (ntifs.h)
description: The FsRtlFastCheckLockForWrite routine determines whether the specified process has write access to a locked byte range of a file.
old-location: ifsk\fsrtlfastchecklockforwrite.htm
tech.root: ifsk
ms.assetid: 4b4295dd-0d4b-4d41-a2ca-f09fe2d8d8b2
ms.date: 03/29/2018
keywords: ["FsRtlFastCheckLockForWrite function"]
ms.keywords: FsRtlFastCheckLockForWrite, FsRtlFastCheckLockForWrite routine [Installable File System Drivers], fsrtlref_1f8feaa8-cc2d-47fb-af4a-00ef0efb4190.xml, ifsk.fsrtlfastchecklockforwrite, ntifs/FsRtlFastCheckLockForWrite
f1_keywords:
 - "ntifs/FsRtlFastCheckLockForWrite"
 - "FsRtlFastCheckLockForWrite"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlFastCheckLockForWrite
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlFastCheckLockForWrite function


## -description


The <b>FsRtlFastCheckLockForWrite</b> routine determines whether the specified process has write access to a locked byte range of a file.


## -parameters




### -param FileLock 
[in]
A pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a> or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>.


### -param StartingByte 
[in]
A pointer to a variable that specifies the starting byte offset within the file of the byte range to check.


### -param Length 
[in]
A pointer to a variable that specifies the length, in bytes, of the range to check.


### -param Key 
[in]
The key for the byte range lock.


### -param FileObject 
[in]
A pointer to the file object for the file.


### -param ProcessId 
[in]
A pointer to the process ID for the process.


## -returns



The <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforwrite">FsRtlFastCheckLockForWrite</a> routine returns <b>TRUE</b> if the specified process has write access, <b>FALSE</b> otherwise.




## -see-also




<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforread">FsRtlFastCheckLockForRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>
 

 