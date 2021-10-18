---
UID: NF:wdm.MmAllocateContiguousMemoryEx
tech.root: kernel
title: MmAllocateContiguousMemoryEx
ms.date: 06/03/2021
targetos: Windows
description: The MmAllocateContiguousMemoryEx function allocates a range of physically contiguous non-paged memory and returns its virtual address.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - MmAllocateContiguousMemoryEx
f1_keywords:
 - MmAllocateContiguousMemoryEx
 - wdm/MmAllocateContiguousMemoryEx
dev_langs:
 - c++
---

## -description

The **MmAllocateContiguousMemoryEx** function allocates a range of physically contiguous non-paged memory and returns its virtual address.

## -parameters

### -param NumberOfBytes

[in]
On entry, supplies the number of bytes to allocate. On successful return, receives the amount allocated.

### -param LowestAcceptableAddress

[in]
Supplies the lowest physical address which is valid for the allocation. For example, if the device can only reference physical memory in the 8M to 16MB range, this value would be set to 0x800000 (8Mb).

### -param HighestAcceptableAddress

[in]
Supplies the highest physical address which is valid for the allocation. For example, if the device can only reference physical memory below 16MB, this value would be set to 0xFFFFFF (16Mb - 1).

### -param BoundaryAddressMultiple

[in]
Supplies the physical address multiple this allocation must not cross.

### -param PreferredNode

[in]
Supplies the preferred node the allocation should be made from if pages are available on that node. MM_ANY_NODE_OK is used to signify no node preference.

### -param Protect

[in]
Supplies the desired protection (including cache type) for the mapping.

### -param PartitionObject

[in, optional]
If specified, supplies a partition object to allocate the physical memory from.  If not specified, the memory will come from the system partition.

### -param Tag

[in]
Supplies the tag for the allocation.

### -param Flags

[in]
Various flags:

- **MM_ALLOCATE_CONTIGUOUS_MEMORY_FAST_ONLY** - Allocate desired contiguous memory only if it can be satisfied quickly. Fail if prolonged physical memory searching and trading must take place to satisfy the allocation.

### -param BaseAddress

[out]
On success, receives the base virtual address of the contiguous memory.

## -returns

Returns an NTSTATUS code.

## -remarks

This memory must be freed with [**MmFreeContiguousMemory**](nf-wdm-mmfreecontiguousmemory.md).

## -see-also

[MmFreeContiguousMemory](nf-wdm-mmfreecontiguousmemory.md)
