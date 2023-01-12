---
UID: NF:ntddk.MmAllocateContiguousMemorySpecifyCacheNode
title: MmAllocateContiguousMemorySpecifyCacheNode function (ntddk.h)
description: The MmAllocateContiguousMemorySpecifyCacheNode routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space.
tech.root: kernel
ms.date: 12/06/2022
keywords: ["MmAllocateContiguousMemorySpecifyCacheNode function"]
ms.keywords: MmAllocateContiguousMemorySpecifyCacheNode, MmAllocateContiguousMemorySpecifyCacheNode routine [Kernel-Mode Driver Architecture], k106_0ccc75e1-5d61-4f89-b576-1c709b50609f.xml, kernel.mmallocatecontiguousmemoryspecifycachenode, wdm/MmAllocateContiguousMemorySpecifyCacheNode
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmAllocateContiguousMemorySpecifyCacheNode
 - ntddk/MmAllocateContiguousMemorySpecifyCacheNode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmAllocateContiguousMemorySpecifyCacheNode
---

## -description

The **MmAllocateContiguousMemorySpecifyCacheNode** routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space.

## -parameters

### -param NumberOfBytes [in]

The size, in bytes, of the block of contiguous memory to allocate. For more information, see the **Remarks** section below.

### -param LowestAcceptableAddress [in]

The lowest valid physical address the caller can use. For example, if a device can address only locations above the first 8 megabytes of the processor's physical memory address range, the driver for this device  should set *LowestAcceptableAddress* to 0x0000000000800000.

### -param HighestAcceptableAddress [in]

The highest valid physical address the caller can use. For example, if a device can address only locations in the first 16 megabytes of the processor's physical memory address range, the driver for this device should set *HighestAcceptableAddress* to 0x0000000000FFFFFF.

### -param BoundaryAddressMultiple [in, optional]

The physical address multiple that the allocated buffer must not cross. A physical address multiple must always be a power of two. This parameter is optional and can be specified as zero to indicate that the device has no special memory boundary restrictions. For more information, see Remarks.

### -param CacheType [in]

Specifies a [MEMORY_CACHING_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type) value, which indicates the type of caching requested for the contiguous physical memory.

### -param PreferredNode [in]

The preferred node number. If a multiprocessor system contains N nodes, the nodes are numbered 0 to N-1. If MM_ANY_NODE_OK is specified or the machine only has one node, then the allocation is satisfied from any node. Otherwise, the allocation is made from the preferred node or if a satisfactory range cannot be found from the preferred node, then **NULL** is returned.

## -returns

**MmAllocateContiguousMemorySpecifyCacheNode** returns the base virtual address for the allocated memory. If the request cannot be satisfied, the routine returns **NULL**.

## -remarks

A kernel-mode device driver calls this routine  to allocate a contiguous block of physical memory. In a non-uniform memory access (NUMA) multiprocessor system, the caller can specify a preferred node from which to allocate the memory. A node is a collection of processors that share fast access to a region of memory. In a non-NUMA multiprocessor or a single-processor system, **MmAllocateContiguousMemorySpecifyCacheNode** treats all memory as belonging to a single node and allocates memory from this node.

**MmAllocateContiguousMemorySpecifyCacheNode** allocates a block of nonpaged memory that is contiguous in physical address space. The routine maps this block to a contiguous block of virtual memory in the system address space and returns the virtual address of the base of this block. The routine aligns the starting address of a contiguous memory allocation to a memory page boundary.

Drivers must not access memory beyond the requested allocation size. For example, developers should not assume that their drivers can safely use memory between the end of their requested allocation and the next page boundary.

Because contiguous physical memory is usually in short supply, it should be used sparingly and only when necessary. A driver that must use contiguous memory should allocate this memory during driver initialization because physical memory is likely to become fragmented over time as the operating system allocates and frees memory. Typically, a driver calls **MmAllocateContiguousMemorySpecifyCacheNode** from its [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine to allocate an internal buffer for long-term use, and frees the buffer just before the driver is unloaded.

Memory allocated by **MmAllocateContiguousMemorySpecifyCacheNode** must be freed when the memory is no longer needed. Call the [MmFreeContiguousMemory](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmfreecontiguousmemory) routine to free memory that is allocated by **MmAllocateContiguousMemorySpecifyCacheNode**.

If you specify a nonzero value for the *BoundaryAddressMultiple* parameter, the physical address range of the allocated memory block will not cross an address boundary that is an integer multiple of this value. A driver should set this parameter to zero unless a nonzero value is required to work around a hardware limitation. For example, if a device cannot transfer data across 16-megabyte physical boundaries, the driver should specify a value of 0x1000000 for this parameter to ensure that the addresses that the device sees do not wrap around at a 16-megabyte boundary.

If you use the **MmAllocateContiguousMemorySpecifyCacheNode** routine on computers with large amounts of memory, the operating system's performance might severely degrade when the system tries to create a contiguous chunk of memory. This degradation is greatly reduced starting with Windows Vista SP1 and Windows Server 2008, but contiguous memory can still be expensive to allocate. For this reason, drivers should avoid repeated calls to **MmAllocateContiguousMemorySpecifyCacheNode**. Instead, drivers should allocate all required contiguous buffers in their **DriverEntry** routines and reuse these buffers.

Memory that **MmAllocateContiguousMemorySpecifyCacheNode** allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).

## -see-also

[DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver)

[MEMORY_CACHING_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type)

[MmFreeContiguousMemory](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmfreecontiguousmemory)
