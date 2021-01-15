---
UID: NF:fltkernel.FltFastIoPrepareMdlWrite
title: FltFastIoPrepareMdlWrite function (fltkernel.h)
description: The FltFastIoPrepareMdlWrite routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.
old-location: ifsk\fltfastiopreparemdlwrite.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltFastIoPrepareMdlWrite function"]
ms.keywords: FltFastIoPrepareMdlWrite, FsRtlPrepareMdlWriteDev, FsRtlPrepareMdlWriteDev routine [Installable File System Drivers], fltkernel/FsRtlPrepareMdlWriteDev, ifsk.fltfastiopreparemdlwrite
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
 - FltFastIoPrepareMdlWrite
 - fltkernel/FltFastIoPrepareMdlWrite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FltFastIoPrepareMdlWrite
---

# FltFastIoPrepareMdlWrite function


## -description

The <b>FltFastIoPrepareMdlWrite</b> routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.

## -parameters

### -param InitiatingInstance

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

### -param FileObject 

[in]
A pointer to the file object.

### -param FileOffset 

[in]
A pointer to a value that specifies the starting byte offset within the cache that holds the data.

### -param Length 

[in]
The length in bytes of the data to read from the cache.

### -param LockKey 

[in]
A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked non-exclusively, the value in this parameter must be the key for that nonexclusive lock. The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.

### -param MdlChain 

[out]
On output, a pointer to a linked list of memory descriptor lists (MDLs) that point to the byte range within the cached data.

### -param IoStatus 

[out]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.

## -returns

The <b>FltFastIoPrepareMdlWrite</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails.

## -remarks

<b>FltFastIoPrepareMdlWrite</b> is similar to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite">FsRtlCopyWrite</a>, except that <b>FltFastIoPrepareMdlWrite</b> does not copy data to the cache. Instead, the physical pages that the caller will overwrite are locked in memory, and <b>FltFastIoPrepareMdlWrite</b> returns one or more memory descriptor lists (MDLs) that point to the specified byte range. The locked pages remain locked until the caller calls <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlwritecomplete">FltFastIoMdlWriteComplete</a>.

The pages that the MDLs point to are locked in memory, but are not mapped in system space. The caller can perform this mapping by calling <a href="/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetsystemaddressformdlsafe">MmGetSystemAddressForMdlSafe</a>.

Even if the call to <b>FltFastIoPrepareMdlWrite</b> fails, one or more MDLs might have been allocated. The caller can examine the value of <i>IoStatus.Information</i> to determine if this has occurred. If it has, the caller must call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlwritecomplete">FltFastIoMdlWriteComplete</a> to free the allocated MDLs.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiomdlwritecomplete">FltFastIoMdlWriteComplete</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite">FsRtlCopyWrite</a>



<a href="/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetsystemaddressformdlsafe">MmGetSystemAddressForMdlSafe</a>

