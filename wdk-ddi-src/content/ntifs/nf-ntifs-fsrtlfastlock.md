---
UID: NF:ntifs.FsRtlFastLock
title: FsRtlFastLock macro (ntifs.h)
description: The FsRtlFastLock macro is used by file systems and filter drivers to request a byte-range lock for a file stream.
old-location: ifsk\fsrtlfastlock.htm
tech.root: ifsk
ms.date: 09/10/2021
keywords: ["FsRtlFastLock macro"]
ms.keywords: FsRtlFastLock, FsRtlFastLock function [Installable File System Drivers], fsrtlref_c60db87b-ac5a-4c60-83f2-7381e0156806.xml, ifsk.fsrtlfastlock, ntifs/FsRtlFastLock
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlFastLock
 - ntifs/FsRtlFastLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlFastLock
---

# FsRtlFastLock macro

## -description

The **FsRtlFastLock** macro is used by file systems and filter drivers to request a byte-range lock for a file stream.

## -parameters

### -param A1

**FileLock**: Pointer to the [**FILE_LOCK**](/windows-hardware/drivers/ifs/file-lock) structure for the file. This structure must have been initialized by a previous call to [**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md) or [**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md).

### -param A2

**FileObject**: Pointer to the [**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md) for the open file. The file object must have been created with GENERIC_READ or GENERIC_WRITE access to the file (or both).

### -param A3

**FileOffset**: Pointer to a variable that specifies the starting byte offset within the file of the range to be locked.

### -param A4

**Length**: Pointer to a variable that specifies the length in bytes of the range to be locked.

### -param A5

**ProcessId**: Pointer to the [**EPROCESS**](/windows-hardware/drivers/kernel/eprocess) process ID for the process requesting the byte-range lock.

### -param A6

**Key**: The key to be assigned to the byte-range lock.

### -param A7

**FailImmediately**: Boolean value that specifies whether the lock request should fail if the lock cannot be granted immediately. If the caller can be put into a wait state until the request is granted, set **FailImmediately** to **FALSE**. If it cannot, set **FailImmediately** to **TRUE**.

### -param A8

**ExclusiveLock**: Set to **TRUE** if an exclusive lock is requested, **FALSE** if a shared lock is requested.

### -param A9

**Iosb**: Pointer to a caller-allocated [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that receives status information about the lock request.

### -param A10

**Context**: Optional pointer to a context to use when releasing the byte-range lock.

### -param A11

**AlreadySynchronized**: This parameter is obsolete, but is retained for compatibility with legacy drivers.

## -remarks

The **FsRtlFastLock** macro causes the caller to acquire a byte-range lock on a region of the specified file.

A return value of **TRUE** indicates that the IO_STATUS_BLOCK structure pointed to by **Iosb** received status information about the lock operation. To examine the contents of this structure, use the NT_STATUS macro.

## -see-also

[**FsRtlAllocateFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md)

[**FsRtlInitializeFileLock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md)
