---
UID: NF:ntifs.FsRtlCopyWrite
title: FsRtlCopyWrite function (ntifs.h)
description: Learn more about the FsRtlCopyWrite function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlCopyWrite function"]
ms.keywords: FsRtlCopyWrite, FsRtlCopyWrite routine [Installable File System Drivers], fsrtlref_4c9bfba8-1946-430f-b242-7228394923de.xml, ifsk.fsrtlcopywrite, ntifs/FsRtlCopyWrite
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlCopyWrite
 - ntifs/FsRtlCopyWrite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlCopyWrite
dev_langs:
 - c++
---

# FsRtlCopyWrite function

## -description

The **FsRtlCopyWrite** routine copies data from a user buffer to a cached file.

## -parameters

### -param FileObject [in]

A pointer to a file object for the cached file to which the data is to be written.

### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file.

### -param Length [in]

The length in bytes of the data to be written.

### -param Wait [in]

Set to TRUE if the caller can be put into a wait state until all the data has been copied, FALSE otherwise.

### -param LockKey [in]

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked nonexclusively, the value in this parameter must be the key for that nonexclusive lock The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.

### -param Buffer [in]

A pointer to the buffer from which the data is to be copied.

### -param IoStatus [out]

A pointer to a caller-allocated structure that receives the final completion status and information about the operation. If the data is copied successfully, **IoStatus.Status** contains STATUS_SUCCESS. If not all of the data is copied successfully, **IoStatus.Information** contains the actual number of bytes that were copied.

### -param DeviceObject [in]

A pointer to the device object for the mounted volume that holds the file data.

## -returns

**FsRtlCopyWrite** returns TRUE if the copy request was completed, FALSE otherwise. Note that a return value of TRUE does not necessarily mean that the copy operation was successful.

If **FsRtlCopyWrite** returns FALSE, or if the contents of **IoStatus** indicate that the copy operation failed, the caller must allocate a write IRP instead of calling **FsRtlCopyWrite**.

## -remarks

Rather than implementing a file-system-specific fast I/O write routine, developers of file systems that support file caching should consider using **FsRtlCopyWrite** as the file system's entry point for processing fast I/O write requests. This requires that the file system's **DriverEntry** routine set the FastIoWrite entry point to **FsRtlCopyWrite** in the FAST_IO_DISPATCH structure of the file system driver object. In addition, the file system must do the following:

1. For each file on which fast I/O might be performed, the file system must allocate and initialize an FSRTL_COMMON_FCB_HEADER structure.

   In most file systems, this is accomplished by including the FSRTL_COMMON_FCB_HEADER structure in a file control block (FCB) or comparable structure that is used to maintain the state of an open file.

   Storage for the FSRTL_COMMON_FCB_HEADER structure is typically allocated from paged pool.

2. For each file on which fast I/O might be performed, the file system must link any file objects for the file to the FSRTL_COMMON_FCB_HEADER structure. This is done by setting each file object's **FsContext** member to point to this structure (or to the FCB or other structure that contains the FSRTL_COMMON_FCB_HEADER structure).

3. When caching a file, the file system must set the **IsFastIoPossible** member of the file's FSRTL_COMMON_FCB_HEADER structure to an appropriate value. This value should be updated as needed for as long as the file remains cached.

   In particular, file systems should set the **IsFastIoPossible** member of the FSRTL_COMMON_FCB_HEADER structure to **FastIoIsQuestionable** as soon as any exclusive byte range lock on the cached file exists.

If **Wait** is TRUE, **FsRtlCopyWrite** is guaranteed to copy the data and return TRUE. If the required pages of the cached file are already resident in memory, the data will be copied immediately and no blocking will occur. If any needed pages are not resident, the caller will be put into a wait state until all required pages have been made resident and the data can be copied.

If **Wait** is FALSE, **FsRtlCopyWrite** will refuse to block, and will return FALSE, if it cannot acquire the file's main resource or if the required pages of the cached file are not already resident in memory.

The file system's **FastIoCheckIfPossible** routine is responsible for ensuring that the byte range defined by **FileOffset** and **Length** does not include any exclusively locked byte range for which the caller does not pass the appropriate **LockKey** value. If the file system uses the **FsRtl*Xxx*Lock*Yyy*** support routines to manage byte-range locks, this can be accomplished by calling [**FsRtlFastCheckLockForWrite**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforwrite.md) from the **FastIoCheckIfPossible** routine before calling **FsRtlCopyRead**.

To cache a file, use the [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md) routine.

## -see-also

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)

[**FsRtlCopyRead**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread.md)

[**FsRtlFastCheckLockForWrite**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforwrite.md)
