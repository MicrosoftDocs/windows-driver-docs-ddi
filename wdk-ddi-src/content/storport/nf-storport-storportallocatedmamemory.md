---
UID: NF:storport.StorPortAllocateDmaMemory
title: StorPortAllocateDmaMemory function
author: windows-driver-content
description: This function is the extended version of the StorPortAllocateContiguousMemorySpecifyCacheNode function. It allocates a range of physically contiguous noncached, nonpaged memory, and returns the physical address of the allocated buffer.
ms.assetid: f56640ac-4a31-4384-86bf-423fb7c5cd21
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
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
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtosKrnl.exe
api_name: 
-	StorPortAllocateDmaMemory
product: Windows
targetos: Windows

---

# StorPortAllocateDmaMemory function


## -description

This function is the extended version of the [StorPortAllocateContiguousMemorySpecifyCacheNode function](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/storport/nf-storport-storportallocatecontiguousmemoryspecifycachenode). It allocates a range of physically contiguous noncached, nonpaged memory, and returns the physical address of the allocated buffer.

## -parameters

### -param HwDeviceExtension

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param NumberOfBytes

The number of bytes to allocate.

### -param LowestAcceptableAddress

The lowest physical address that is valid for the allocation. For example, if the device can only reference physical memory in the 8 MB to 16 MB range, this value would be set to 0x800000 (8 MB).

### -param HighestAcceptableAddress

The highest physical address that is valid for the allocation. For example, if the device can only reference physical memory below 16 MB, this value would be set to 0xFFFFFF (16 MB - 1).

### -param BoundaryAddressMultiple

The physical address multiple that this allocation must not cross.

### -param CacheType

The desired cache type for the mapping.

### -param PreferredNode

The preferred node from which the allocation should be made if pages are available on that node.

### -param BufferPointer

The variable that receives the starting address of the allocated memory block. Upon return from this routine, if this variable is zero, a contiguous range could not be found to satisfy the request. If this variable is not NULL, it contains a pointer (for example, a virtual address in the nonpaged portion of the system) to the allocated physically contiguous memory.

### -param PhysicalAddress

Physical address of the allocated memory block.

## -returns
This function returns a STOR_STATUS code.


<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed to allocate the requested memory because of insufficient resources.

</td>
</tr>
</table>

## -remarks

If the request fails, BufferPointer will be set to NULL.

## -see-also