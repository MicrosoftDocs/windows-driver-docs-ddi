---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlMdlReadDev~r6
title: FsRtlMdlReadDev function
author: windows-driver-content
description: The FltFastIoMdlRead routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache.
old-location: ifsk\fltfastiomdlread.htm
tech.root: ifsk
ms.assetid: 1DF810B5-D4C3-4F67-B913-C2B2132DFDE2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlMdlReadDev, FsRtlMdlReadDev routine [Installable File System Drivers], fltkernel/FsRtlMdlReadDev, ifsk.fltfastiomdlread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlMdlReadDev
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlMdlReadDev function


## -description


The <b>FltFastIoMdlRead</b> routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache.


## -parameters




### -param FileObject [in]

A pointer to a file object for the cached file.


### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file that holds the data.


### -param Length [in]

The length in bytes of the data to read from the cache.


### -param LockKey [in]

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked non-exclusively, the value in this parameter must be the key for that nonexclusive lock The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.


### -param MdlChain [out]

On output, a pointer to a linked list of memory descriptor lists (MDLs).


### -param IoStatus [out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.


### -param DeviceObject

<p>A pointer to an <a href="https://msdn.microsoft.com/library/Ff550671(v=VS.85).aspx"><b>IO_STATUS_BLOCK</b></a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.</p>




#### - InitiatingInstance

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>.


## -returns



The <b>FltFastIoMdlRead</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails.




## -remarks



The <b>FltFastIoMdlRead</b> routine bypasses the usual IRP mechanism and returns a linked list of memory descriptor lists (MDL) that the caller can use to directly access the cached file data. This operation does not copy or buffer data and therefore is much faster than a normal read.

The routine is similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff546960">FsRtlMdlReadDev</a>. <b>FltFastIoMdlRead</b>, <b>CcMdlRead</b>, and <b>FsRtlMdlReadDev</b> lock the pages that contain the cached file data to prevent the system from swapping these pages to the page file. The pages remain locked in memory until the caller invokes the <a href="https://msdn.microsoft.com/library/windows/hardware/hh706189">FltFastIoMdlReadComplete</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh706189">FltFastIoMdlReadComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546960">FsRtlMdlReadDev</a>
 

 

