---
UID: NF:fltkernel.FltAllocatePoolAlignedWithTag
title: FltAllocatePoolAlignedWithTag function (fltkernel.h)
description: FltAllocatePoolAlignedWithTag allocates a device-aligned buffer for use in a noncached I/O operation.
old-location: ifsk\fltallocatepoolalignedwithtag.htm
tech.root: ifsk
ms.assetid: ffb1493f-6076-4b93-8431-b3ffd4679f96
ms.date: 04/16/2018
keywords: ["FltAllocatePoolAlignedWithTag function"]
ms.keywords: FltAllocatePoolAlignedWithTag, FltAllocatePoolAlignedWithTag function [Installable File System Drivers], FltApiRef_a_to_d_b617aed0-5103-4a1e-aa0d-86247d99e803.xml, fltkernel/FltAllocatePoolAlignedWithTag, ifsk.fltallocatepoolalignedwithtag
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - FltAllocatePoolAlignedWithTag
 - fltkernel/FltAllocatePoolAlignedWithTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltAllocatePoolAlignedWithTag
---

# FltAllocatePoolAlignedWithTag function


## -description

<b>FltAllocatePoolAlignedWithTag</b> allocates a device-aligned buffer for use in a noncached I/O operation.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for a caller-owned minifilter driver instance that is attached to the volume. This parameter is required and cannot be <b>NULL</b>.

### -param PoolType 

[in]
Type of pool to allocate. One of the following: 

<b>NonPagedPool</b>

<b>PagedPool</b>

<b>NonPagedPoolCacheAligned</b>

<b>PagedPoolCacheAligned</b>

See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a> for a description of the available pool memory types.

### -param NumberOfBytes 

[in]
Number of bytes to allocate. This parameter is required and can be zero.

### -param Tag 

[in]
Specifies the pool tag for the allocated memory. Drivers normally specify the pool tag as a string of one to four 7-bit ASCII characters, delimited by single quotation marks (for example, 'abcd'). This parameter is required and cannot be zero.

## -returns

If not enough free pool is available to satisfy the request, <b>FltAllocatePoolAlignedWithTag</b> returns a <b>NULL</b> pointer. Otherwise, <b>FltAllocatePoolAlignedWithTag</b> returns a pointer to the newly allocated buffer.

## -remarks

<b>FltAllocatePoolAlignedWithTag</b> allocates a buffer that is aligned in accordance with the underlying device for the given volume. Such device-aligned buffers are required for noncached I/O. (They can also be used for cached I/O.) Thus when calling routines that perform noncached I/O, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile">FltReadFile</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a>, minifilter drivers should call <b>FltAllocatePoolAlignedWithTag</b> instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>. 

If the caller specifies a value of zero for the <i>NumberOfBytes</i> parameter, <b>FltAllocatePoolAlignedWithTag</b> allocates the smallest amount of memory that meets the alignment requirement. 

The system associates the pool tag specified by the <i>Tag</i> parameter with the allocated buffer. Programming tools, such as the Windows Debugger (WinDbg), can display the pool tag associated with each allocated buffer. The value of the pool tag is normally displayed in reversed order. For example, if a caller passes 'Fred' as the value of the <i>Tag</i> parameter, this value would appear as 'derF' if pool is dumped or when tracking pool usage in the debugger. 

For more information about memory management, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-memory-for-drivers">Memory Management</a>. 

When the buffer that <b>FltAllocatePoolAlignedWithTag</b> allocates is no longer needed, the caller is responsible for freeing it by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreepoolalignedwithtag">FltFreePoolAlignedWithTag</a>. 

Callers of <b>FltAllocatePoolAlignedWithTag</b> can be running at IRQL DISPATCH_LEVEL only if a NonPaged<i>XxxPoolType</i> is specified. Otherwise, callers must be running at IRQL <= APC_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreepoolalignedwithtag">FltFreePoolAlignedWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile">FltReadFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a>

