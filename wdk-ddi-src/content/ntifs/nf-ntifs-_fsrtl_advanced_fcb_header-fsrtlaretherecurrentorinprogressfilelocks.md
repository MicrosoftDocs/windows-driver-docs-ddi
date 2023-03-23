---
UID: NF:ntifs.FsRtlAreThereCurrentOrInProgressFileLocks
title: FsRtlAreThereCurrentOrInProgressFileLocks function (ntifs.h)
description: TheFsRtlAreThereCurrentOrInProgressFileLocks routine determines if there are byte range locks assigned to a file or any lock operations in progress for that file.
old-location: ifsk\fsrtlaretherecurrentorinprogressfilelocks.htm
tech.root: ifsk
ms.date: 03/20/2023
keywords: ["FsRtlAreThereCurrentOrInProgressFileLocks function"]
ms.keywords: FsRtlAreThereCurrentOrInProgressFileLocks, FsRtlAreThereCurrentOrInProgressFileLocks routine [Installable File System Drivers], fsrtlref_66517730-628e-4aa4-b3c0-b5c0e0fd4d7d.xml, ifsk.fsrtlaretherecurrentorinprogressfilelocks, ntifs/FsRtlAreThereCurrentOrInProgressFileLocks
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
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

The**FsRtlAreThereCurrentOrInProgressFileLocks** routine determines if there are byte range locks assigned to a file or any lock operations in progress for that file.

## -parameters

### -param FileLock [in]

A pointer to the [**FILE_LOCK**](ns-ntifs-file_lock.md) structure for the file to be checked.

## -returns

The routine returns TRUE when there are any byte range locks assigned to the file or when there are byte range lock requests in progress for the file. Otherwise, the routine returns FALSE.

## -remarks

File systems can use the **FsRtlAreThereCurrentOrInProgressFileLocks** routine in [Oplock Semantics](/windows-hardware/drivers/ifs/oplock-semantics) to determine whether to grant a shared oplock.

## -see-also

[**FILE_LOCK**](ns-ntifs-file_lock.md)

[**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md)

[**FsRtlGetNextFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextfilelock.md)

[**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md)
