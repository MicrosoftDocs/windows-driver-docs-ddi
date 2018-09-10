---
UID: NS:d3dkmddi._DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
title: _DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
author: windows-driver-content
description: Arguments used in the DXGKCB_ALLOCATECONTIGUOUSMEMORY callback function, to allocate contiguous memory.
ms.assetid: dce7b187-8ebf-4309-8769-29536b908e76
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARGCB_ALLOCATECONTIGUOUSMEMORY, DXGKARGCB_ALLOCATECONTIGUOUSMEMORY, *INOUT_PDXGKARGCB_ALLOCATECONTIGUOUSMEMORY
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	_DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGKARGCB_ALLOCATECONTIGUOUSMEMORY structure

## -description

Arguments used in the [DXGKCB_ALLOCATECONTIGUOUSMEMORY](nc-d3dkmddi-dxgkcb_allocatecontiguousmemory.md) callback function, to allocate contiguous memory.

## -struct-fields

### -field NumberOfBytes

The size, in bytes, of the block of contiguous memory to allocate.

### -field LowestAcceptableAddress

The lowest valid physical address the caller can use. For example, if a device can address only locations above the first 8 megabytes of the processor's physical memory address range, the driver for this device should set LowestAcceptableAddress to 0x0000000000800000.

### -field HighestAcceptableAddress

The highest valid physical address the caller can use. For example, if a device can address only locations in the first 16 megabytes of the processor's physical memory address range, the driver for this device should set HighestAcceptableAddress to 0x0000000000FFFFFF.

### -field BoundaryAddressMultiple

The physical address multiple that the allocated buffer must not cross. A physical address multiple must always be a power of two. This parameter is optional and can be specified as zero to indicate that the device has no special memory boundary restrictions.

### -field CacheType

The cache type of the pages to allocate. Valid values include non-cached, cached, or writecombined.

### -field hMemoryHandle

A Dxgkrnl tracking handle for the allocation. This value should be passed to the corresponding [DGXKCB_FREECONTIGUOUSMEMORY](nc-d3dkmddi-dxgkcb_freecontiguousmemory.md) callback function.

### -field pMemory

A contiguous chunk of non-paged physical memory guaranteed to be mapped to the IoMmu for its lifetime.

## -remarks

## -see-also

[DXGKCB_ALLOCATECONTIGUOUSMEMORY](nc-d3dkmddi-dxgkcb_allocatecontiguousmemory.md)
