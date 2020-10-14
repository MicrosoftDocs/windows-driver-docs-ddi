---
UID: NF:ntifs.FsRtlPrepareMdlWriteDev
title: FsRtlPrepareMdlWriteDev function (ntifs.h)
description: The FsRtlPrepareMdlWriteDev routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.
old-location: ifsk\fltfastiopreparemdlwrite.htm
tech.root: ifsk
ms.assetid: 7C48D179-35FA-44E1-B959-BD857AAA28E1
ms.date: 04/16/2018
keywords: ["FsRtlPrepareMdlWriteDev function"]
ms.keywords: FsRtlPrepareMdlWriteDev, FsRtlPrepareMdlWriteDev routine [Installable File System Drivers], fltkernel/FsRtlPrepareMdlWriteDev
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlPrepareMdlWriteDev
 - ntifs/FsRtlPrepareMdlWriteDev
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlPrepareMdlWriteDev
dev_langs:
 - c++
---

# FsRtlPrepareMdlWriteDev function


## -description

The **FsRtlPrepareMdlWriteDev** routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.

## -parameters

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
A pointer to an [IO_STATUS_BLOCK](../wdm/ns-wdm-_io_status_block.md) structure that, on output, contains the status of the transfer. If the operation succeeds, ***IoStatus.Status*** is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. ***IoStatus.Information*** is set to the actual number of bytes that the routine successfully locked.

### -param DeviceObject

[ in, optional ] A pointer to a device object on which the file is opened.

## -returns

The **FsRtlPrepareMdlWriteDev** routine returns **TRUE** if the operation succeeds and **FALSE** if the operation fails.

## -remarks

**FsRtlPrepareMdlWriteDev** is similar to [FsRtlCopyWrite](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite.md), except that **FsRtlPrepareMdlWriteDev** does not copy data to the cache. Instead, the physical pages that the caller will overwrite are locked in memory, and **FsRtlPrepareMdlWriteDev** returns one or more memory descriptor lists (MDLs) that point to the specified byte range. The locked pages remain locked until the caller calls [FsRtlMdlWriteCompleteDev](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlwritecompletedev.md).

The pages that the MDLs point to are locked in memory, but are not mapped in system space. The caller can perform this mapping by calling [MmGetSystemAddressForMdlSafe](/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetsystemaddressformdlsafe).

Even if the call to **FsRtlPrepareMdlWriteDev** fails, one or more MDLs might have been allocated. The caller can examine the value of ***IoStatus.Information*** to determine if this has occurred. If it has, the caller must call [FsRtlMdlWriteCompleteDev](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlwritecompletedev.md) to free the allocated MDLs.

## -see-also

[FsRtlMdlWriteCompleteDev](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlwritecompletedev.md)



[FsRtlCopyWrite](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite.md)



[MmGetSystemAddressForMdlSafe](/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetsystemaddressformdlsafe)
