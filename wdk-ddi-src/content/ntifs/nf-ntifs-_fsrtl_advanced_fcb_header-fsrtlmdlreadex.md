---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlMdlReadEx
title: FsRtlMdlReadEx function
author: windows-driver-content
description: The FsRtlMdlReadEx routine performs a fast cached MDL read. If the requested data is not cached, the routine reverts to an IRP based MDL read operation.
old-location: ifsk\fsrtlmdlreadex.htm
tech.root: ifsk
ms.assetid: E1F16454-C8E6-4291-83BB-F4CF18F6DF10
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlMdlReadEx, FsRtlMdlReadEx routine [Installable File System Drivers], ifsk.fsrtlmdlreadex, ntifs/FsRtlMdlReadEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlMdlReadEx
product:
-	Windows
targetos: Windows
req.typenames: 
---

# FsRtlMdlReadEx function


## -description


The <b>FsRtlMdlReadEx</b> routine performs a fast cached MDL read.  If the requested data is not cached, the routine reverts to an IRP based MDL read operation.


## -parameters




### -param FileObject [in]

A pointer to the file object.


### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file that holds the data.


### -param Length [in]

The length in bytes of the data to read from the cache.


### -param LockKey [in]

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked nonexclusively, the value in this parameter must be the key for that nonexclusive lock The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.


### -param MdlChain [out]

On output, a pointer to a linked list of memory descriptor lists (MDLs).


### -param IoStatus [out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to <b>STATUS_SUCCESS</b>. Otherwise, it is set to an appropriate <b>NTSTATUS</b> error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.


## -returns



<b>FsRtlMdlReadEx</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The IRP for an the IRP based read could not be allocated.

</td>
</tr>
</table>
 




## -remarks



If fast I/O is available from the file system, the <b>FsRtlMdlReadEx</b> routine will bypass the usual IRP read mechanism and return a linked list of memory descriptor lists (MDL) that the caller can use to directly access the cached file data. This operation does not copy or buffer data and therefore is much faster than a normal read. If fast I/O is not enabled, <b>FsRtlMdlReadEx</b> will generate a synchronous IRP based MDL read and return the MDLs from the request.

The pages described by the MDLs are locked in memory, but not mapped in system space. The caller can perform this mapping by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>. 

Similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>, the <b>FsRtlMdlReadEx</b> routine locks the pages that contain the cached file data to prevent the system from swapping these pages to the page file. The pages remain locked in memory until the caller invokes the <b>CcMdlReadComplete</b> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539163">CcMdlReadComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>
 

 

