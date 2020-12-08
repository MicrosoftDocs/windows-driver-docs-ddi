---
UID: NF:ntifs.FsRtlAreThereCurrentOrInProgressFileLocks
title: FsRtlAreThereCurrentOrInProgressFileLocks function (ntifs.h)
description: TheFsRtlAreThereCurrentOrInProgressFileLocks routine determines if there are byte range locks assigned to a file or any lock operations in progress for that file.
old-location: ifsk\fsrtlaretherecurrentorinprogressfilelocks.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlAreThereCurrentOrInProgressFileLocks function"]
ms.keywords: FsRtlAreThereCurrentOrInProgressFileLocks, FsRtlAreThereCurrentOrInProgressFileLocks routine [Installable File System Drivers], fsrtlref_66517730-628e-4aa4-b3c0-b5c0e0fd4d7d.xml, ifsk.fsrtlaretherecurrentorinprogressfilelocks, ntifs/FsRtlAreThereCurrentOrInProgressFileLocks
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlAreThereCurrentOrInProgressFileLocks
 - ntifs/FsRtlAreThereCurrentOrInProgressFileLocks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlAreThereCurrentOrInProgressFileLocks
---

# FsRtlAreThereCurrentOrInProgressFileLocks function


## -description

The<b>FsRtlAreThereCurrentOrInProgressFileLocks </b>routine determines if there are byte range locks assigned to a file or any lock operations in progress for that file.

## -parameters

### -param FileLock 

[in]
A pointer to the <a href="/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure for the file to be checked.

## -returns

The routine returns <b>TRUE</b> when there are any byte range locks assigned to the file or when there are byte range lock requests in progress for the file. Otherwise, the routine returns <b>FALSE</b>.

## -remarks

File systems can use the <b>FsRtlAreThereCurrentOrInProgressFileLocks</b> routine in <a href="/windows-hardware/drivers/ifs/oplock-semantics">Oplock Semantics</a> to determine whether to grant a shared oplock.

## -see-also

<a href="/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextfilelock">FsRtlGetNextFileLock</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>



<a href="/windows-hardware/drivers/ifs/oplock-semantics">Oplock Semantics</a>
