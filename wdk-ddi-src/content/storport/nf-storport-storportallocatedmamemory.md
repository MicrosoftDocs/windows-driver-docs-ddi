---
UID: NF:storport.StorPortAllocateDmaMemory
title: StorPortAllocateDmaMemory function (storport.h)
description: This function is the extended version of the StorPortAllocateContiguousMemorySpecifyCacheNode function. It allocates a range of physically contiguous noncached, nonpaged memory, and returns the physical address of the allocated buffer.
tech.root: storage
ms.date: 05/23/2022
keywords: ["StorPortAllocateDmaMemory function"]
ms.keywords: StorPortAllocateDmaMemory
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - StorPortAllocateDmaMemory
 - storport/StorPortAllocateDmaMemory
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - StorPortAllocateDmaMemory
---

# StorPortAllocateDmaMemory function

## -description

This function is the extended version of the [StorPortAllocateContiguousMemorySpecifyCacheNode function](./nf-storport-storportallocatecontiguousmemoryspecifycachenode.md). It allocates a range of physically contiguous noncached, nonpaged memory, and returns the physical address of the allocated buffer.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param NumberOfBytes [in]

The number of bytes to allocate.

### -param LowestAcceptableAddress [in]

The lowest physical address that is valid for the allocation. For example, if the device can only reference physical memory in the 8 MB to 16 MB range, this value would be set to 0x800000 (8 MB).

### -param HighestAcceptableAddress [in]

The highest physical address that is valid for the allocation. For example, if the device can only reference physical memory below 16 MB, this value would be set to 0xFFFFFF (16 MB - 1).

### -param BoundaryAddressMultiple [in, optional]

The physical address multiple that this allocation must not cross.

### -param CacheType [in]

The desired cache type for the mapping.

### -param PreferredNode [in]

The preferred node from which the allocation should be made if pages are available on that node.

### -param BufferPointer [out]

The variable that receives the starting address of the allocated memory block. Upon return from this routine, if this variable is zero, a contiguous range could not be found to satisfy the request. If this variable is not NULL, it contains a pointer (for example, a virtual address in the nonpaged portion of the system) to the allocated physically contiguous memory.

### -param PhysicalAddress [out]

Physical address of the allocated memory block.

## -returns

This function returns a STOR_STATUS code.

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_NOT_IMPLEMENTED | This function is not implemented on the active operating system. |
| STOR_STATUS_SUCCESS | The operation was successful. |
| STOR_STATUS_INSUFFICIENT_RESOURCES |The operation failed to allocate the requested memory because of insufficient resources. |

## -remarks

If the request fails, BufferPointer will be set to NULL.

## -see-also

[**StorPortFreeDmaMemory**](nf-storport-storportfreedmamemory.md)
