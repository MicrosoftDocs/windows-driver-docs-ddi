---
UID: NF:ntifs.FsRtlAreThereCurrentFileLocks
title: FsRtlAreThereCurrentFileLocks macro (ntifs.h)
description: The FsRtlAreThereCurrentFileLocks macro checks whether any byte range locks exist for the specified file.
old-location: ifsk\fsrtlaretherecurrentfilelocks.htm
tech.root: ifsk
ms.date: 06/27/2019
keywords: ["FsRtlAreThereCurrentFileLocks macro"]
ms.keywords: FsRtlAreThereCurrentFileLocks, FsRtlAreThereCurrentFileLocks function [Installable File System Drivers], fsrtlref_c3102eee-b523-418a-8977-a875e0eb76b7.xml, ifsk.fsrtlaretherecurrentfilelocks, ntifs/FsRtlAreThereCurrentFileLocks
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlAreThereCurrentFileLocks
 - ntifs/FsRtlAreThereCurrentFileLocks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlAreThereCurrentFileLocks
---

# FsRtlAreThereCurrentFileLocks macro


## -description

The **FsRtlAreThereCurrentFileLocks** macro checks whether any byte range locks exist for the specified file.

## -parameters

### -param FL

Pointer to the [FILE_LOCK](/windows-hardware/drivers/ifs/file-lock) structure for the file. This structure must have been initialized by a previous call to [**FsRtlAllocateFileLock**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md) or [**FsRtlInitializeFileLock**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md).

## -remarks

This macro acts like a BOOLEAN function, returning **TRUE** if any byte range locks exist for the specified file or **FALSE** if none exist.

File systems and filter drivers often call **FsRtlAreThereCurrentFileLocks** from their FastIoCheckIfPossible routines.

> [!NOTE]
> If a byte-range lock has existed since the specified file was opened, the **FsRtlAreThereCurrentFileLocks** routine returns **TRUE**,  unless the relevant FILE_LOCK is reinitialized. If a lock was established, and then released, the use of **FsRtlAreThereCurrentFileLocks**  can prevent the assignment of oplocks unnecessarily. Use [**FsRtlAreThereCurrentOrInProgressFileLocks**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlaretherecurrentorinprogressfilelocks.md) to avoid this problem.

## -see-also

[**FsRtlAllocateFileLock**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md)

[**FsRtlAreThereCurrentOrInProgressFileLocks**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlaretherecurrentorinprogressfilelocks.md)

[**FsRtlInitializeFileLock**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md)
