---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlMdlReadDev~r6
title: FsRtlMdlReadDev function
author: windows-driver-content
description: The FsRtlMdlReadDev routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache.
old-location: ifsk\fsrtlmdlreaddev.htm
old-project: ifsk
ms.assetid: f364fc4b-a3c4-4010-a089-59a00ec3f872
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlMdlReadDev, FsRtlMdlReadDev routine [Installable File System Drivers], fsrtlref_0ea7c45a-9056-4a17-9e9f-38608e643172.xml, ifsk.fsrtlmdlreaddev, ntifs/FsRtlMdlReadDev
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlMdlReadDev
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlMdlReadDev function


## -description


The <b>FsRtlMdlReadDev</b> routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache.


## -syntax


````
BOOLEAN FsRtlMdlReadDev(
  _In_     PFILE_OBJECT     FileObject,
  _In_     PLARGE_INTEGER   FileOffset,
  _In_     ULONG            Length,
  _In_     ULONG            LockKey,
  _Out_    PMDL             *MdlChain,
  _Out_    PIO_STATUS_BLOCK IoStatus,
  _In_opt_ PDEVICE_OBJECT   DeviceObject
);
````


## -parameters




#### - FileObject [in]

A pointer to a file object for the cached file.


#### - FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file that holds the data.


#### - Length [in]

The length in bytes of the data to read from the cache.


#### - LockKey [in]

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked nonexclusively, the value in this parameter must be the key for that nonexclusive lock The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.


#### - MdlChain [out]

On output, a pointer to a linked list of memory descriptor lists (MDLs).


#### - IoStatus [out]

A pointer to an <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.


#### - DeviceObject [in, optional]

The device object for the device that holds the file data.


## -returns


The <b>FsRtlMdlReadDev</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails.



## -remarks


The <b>FsRtlMdlReadDev</b> routine bypasses the usual IRP mechanism and returns a linked list of memory descriptor lists (MDL) that the caller can use to directly access the cached file data. This operation does not copy or buffer data and therefore is much faster than a normal read.

The routine is similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>. Both <b>FsRtlMdlReadDev</b> and <b>CcMdlRead</b> lock the pages that contain the cached file data to prevent the system from swapping these pages to the page file. The pages remain locked in memory until the caller invokes the <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreadcompletedev~r2.md">FsRtlMdlReadCompleteDev</a> routine.



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreadcompletedev~r2.md">FsRtlMdlReadCompleteDev</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlMdlReadDev routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

