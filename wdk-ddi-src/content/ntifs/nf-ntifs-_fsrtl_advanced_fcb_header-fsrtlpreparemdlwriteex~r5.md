---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlPrepareMdlWriteEx~r5
title: FsRtlPrepareMdlWriteEx function
author: windows-driver-content
description: The FsRtlPrepareMdlWriteEx routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.
old-location: ifsk\fsrtlpreparemdlwriteex.htm
old-project: ifsk
ms.assetid: 6A9BBBAD-F6D1-49A4-9FBA-7F263C1793F0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlPrepareMdlWriteEx, FsRtlPrepareMdlWriteEx routine [Installable File System Drivers], ifsk.fsrtlpreparemdlwriteex, ntifs/FsRtlPrepareMdlWriteEx
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlPrepareMdlWriteEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlPrepareMdlWriteEx function


## -description


The <b>FsRtlPrepareMdlWriteEx</b> routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache. If the cache support for the write is not available, the routine reverts to an IRP based MDL write operation.


## -syntax


````
NTSTATUS FsRtlPrepareMdlWriteEx(
  _In_  PFILE_OBJECT     FileObject,
  _In_  PLARGE_INTEGER   FileOffset,
  _In_  ULONG            Length,
  _In_  ULONG            LockKey,
  _Out_ PMDL             *MdlChain,
  _Out_ PIO_STATUS_BLOCK IoStatus
);
````


## -parameters




### -param FileObject [in]

A pointer to the file object.


### -param FileOffset [in]

A pointer to a value that specifies the starting byte offset within the cache that holds the data.


### -param Length [in]

The length in bytes of the data to write to the cache.


### -param LockKey [in]

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked nonexclusively, the value in this parameter must be the key for that nonexclusive lock. The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.


### -param MdlChain [out]

On output, a pointer to a linked list of memory descriptor lists (MDLs) that point to the byte range within the cached data.


### -param IoStatus [out]

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to <b>STATUS_SUCCESS</b>. Otherwise, it is set to an appropriate <b>NTSTATUS</b> error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.


## -returns



<b>FsRtlPrepareMdlWriteEx</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following: 

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
An IRP for the IRP based write could not be allocated.

</td>
</tr>
</table>
 




## -remarks



If fast I/O is available for the file system, the <b>FsRtlPrepareMdlWriteEx</b> routine will bypass the usual IRP write mechanism and return a linked list of memory descriptor lists (MDL) that the caller can use to write data directly to the file cache. Instead of copying data buffered data into the cache, the physical pages that the caller will overwrite are locked in memory and can be written to directly. <b>FsRtlPrepareMdlWriteEx</b> returns one or more memory descriptor lists (MDLs) that point to the specified byte range.

 If fast I/O is not enabled, <b>FsRtlPrepareMdlWriteEx</b> will generate a synchronous IRP based MDL write prepare and return the MDLs allocated from the request.

The pages that the MDLs point to are locked in memory, but are not mapped in system space. The caller can perform this mapping by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>.

Each call to <b>FsRtlPrepareMdlWriteEx</b> must be followed by a call to <a href="..\ntifs\nf-ntifs-ccmdlwritecomplete.md">CcMdlWriteComplete</a>.




## -see-also

<a href="..\ntifs\nf-ntifs-ccmdlwritecomplete.md">CcMdlWriteComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>



<a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlPrepareMdlWriteEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

