---
UID: NF:fltkernel.FltFastIoMdlRead
title: FltFastIoMdlRead function (fltkernel.h)
description: The FltFastIoMdlRead routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache.
old-location: ifsk\fltfastiomdlread.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltFastIoMdlRead function"]
ms.keywords: FltFastIoMdlRead, FsRtlMdlReadDev, FsRtlMdlReadDev routine [Installable File System Drivers], fltkernel/FsRtlMdlReadDev, ifsk.fltfastiomdlread
req.header: fltkernel.h
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltFastIoMdlRead
 - fltkernel/FltFastIoMdlRead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FltFastIoMdlRead
---

# FltFastIoMdlRead function


## -description

The <b>FltFastIoMdlRead</b> routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache.

## -parameters

### -param InitiatingInstance

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

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


A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.

## -returns

The <b>FltFastIoMdlRead</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails.

## -remarks

The <b>FltFastIoMdlRead</b> routine bypasses the usual IRP mechanism and returns a linked list of memory descriptor lists (MDL) that the caller can use to directly access the cached file data. This operation does not copy or buffer data and therefore is much faster than a normal read.

The routine is similar to <a href="/previous-versions/ff539159(v=vs.85)">CcMdlRead</a> and <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev">FsRtlMdlReadDev</a>. <b>FltFastIoMdlRead</b>, <b>CcMdlRead</b>, and <b>FsRtlMdlReadDev</b> lock the pages that contain the cached file data to prevent the system from swapping these pages to the page file. The pages remain locked in memory until the caller invokes the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlreadcomplete">FltFastIoMdlReadComplete</a> routine.

## -see-also

<a href="/previous-versions/ff539159(v=vs.85)">CcMdlRead</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlreadcomplete">FltFastIoMdlReadComplete</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev">FsRtlMdlReadDev</a>

