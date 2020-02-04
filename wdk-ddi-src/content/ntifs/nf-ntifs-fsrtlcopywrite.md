---
UID: NF:ntifs.FsRtlCopyWrite
title: FsRtlCopyWrite function (ntifs.h)
description: The FsRtlCopyWrite routine copies data from a user buffer to a cached file.
old-location: ifsk\fsrtlcopywrite.htm
tech.root: ifsk
ms.assetid: badff1ac-ccb2-418d-94be-c30d323f0464
ms.date: 04/16/2018
ms.keywords: FsRtlCopyWrite, FsRtlCopyWrite routine [Installable File System Drivers], fsrtlref_4c9bfba8-1946-430f-b242-7228394923de.xml, ifsk.fsrtlcopywrite, ntifs/FsRtlCopyWrite
f1_keywords:
 - "ntifs/FsRtlCopyWrite"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlCopyWrite
product:
- Windows
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlCopyWrite function


## -description


The <b>FsRtlCopyWrite</b> routine copies data from a user buffer to a cached file.


## -parameters




### -param FileObject [in]

A pointer to a file object for the cached file to which the data is to be written.


### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file.


### -param Length [in]

The length in bytes of the data to be written.


### -param Wait [in]

Set to <b>TRUE</b> if the caller can be put into a wait state until all the data has been copied, <b>FALSE</b> otherwise.


### -param LockKey [in]

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked nonexclusively, the value in this parameter must be the key for that nonexclusive lock The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.


### -param Buffer [in]

A pointer to the buffer from which the data is to be copied.


### -param IoStatus [out]

A pointer to a caller-allocated structure that receives the final completion status and information about the operation. If the data is copied successfully, <i>IoStatus.Status</i> contains STATUS_SUCCESS. If not all of the data is copied successfully, <i>IoStatus.Information</i> contains the actual number of bytes that were copied.


### -param DeviceObject [in]

A pointer to the device object for the mounted volume that holds the file data.


## -returns



<b>FsRtlCopyWrite</b>
      returns <b>TRUE</b> if the copy request was completed, <b>FALSE</b> otherwise. Note that a return value of <b>TRUE</b> does not necessarily mean that the copy operation was successful. 

If <b>FsRtlCopyWrite</b> returns <b>FALSE</b>, or if the contents of <i>IoStatus</i> indicate that the copy operation failed, the caller must allocate a write IRP instead of calling <b>FsRtlCopyWrite</b>.




## -remarks



Rather than implementing a file-system-specific fast I/O write routine, developers of file systems that support file caching should consider using <b>FsRtlCopyWrite</b> as the file system's entry point for processing fast I/O write requests. This requires that the file system's <b>DriverEntry</b> routine set the FastIoWrite entry point to <b>FsRtlCopyWrite</b> in the FAST_IO_DISPATCH structure of the file system driver object. In addition, the file system must do the following:

<ol>
<li>
For each file on which fast I/O might be performed, the file system must allocate and initialize an FSRTL_COMMON_FCB_HEADER structure. 

In most file systems, this is accomplished by including the FSRTL_COMMON_FCB_HEADER structure in a file control block (FCB) or comparable structure that is used to maintain the state of an open file.

Storage for the FSRTL_COMMON_FCB_HEADER structure is typically allocated from paged pool. 

</li>
<li>
For each file on which fast I/O might be performed, the file system must link any file objects for the file to the FSRTL_COMMON_FCB_HEADER structure. This is done by setting each file object's <b>FsContext</b> member to point to this structure (or to the FCB or other structure that contains the FSRTL_COMMON_FCB_HEADER structure). 

</li>
<li>
When caching a file, the file system must set the <b>IsFastIoPossible</b> member of the file's FSRTL_COMMON_FCB_HEADER structure to an appropriate value. This value should be updated as needed for as long as the file remains cached.

In particular, file systems should set the <b>IsFastIoPossible</b> member of the FSRTL_COMMON_FCB_HEADER structure to <b>FastIoIsQuestionable</b> as soon as any exclusive byte range lock on the cached file exists.

</li>
</ol>
If <i>Wait</i> is <b>TRUE</b>, <b>FsRtlCopyWrite</b> is guaranteed to copy the data and return <b>TRUE</b>. If the required pages of the cached file are already resident in memory, the data will be copied immediately and no blocking will occur. If any needed pages are not resident, the caller will be put into a wait state until all required pages have been made resident and the data can be copied.

If <i>Wait</i> is <b>FALSE</b>, <b>FsRtlCopyWrite</b> will refuse to block, and will return <b>FALSE</b>, if it cannot acquire the file's main resource or if the required pages of the cached file are not already resident in memory.

The file system's <b>FastIoCheckIfPossible</b> routine is responsible for ensuring that the byte range defined by <i>FileOffset</i> and <i>Length</i> does not include any exclusively locked byte range for which the caller does not pass the appropriate <i>LockKey</i> value. If the file system uses the <b>FsRtl..Lock</b><i>Xxx</i> support routines to manage byte-range locks, this can be accomplished by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlfastchecklockforwrite">FsRtlFastCheckLockForWrite</a> from the <b>FastIoCheckIfPossible</b> routine before calling <b>FsRtlCopyWrite</b>.

To cache a file, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlcopyread">FsRtlCopyRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlfastchecklockforwrite">FsRtlFastCheckLockForWrite</a>
 

 

