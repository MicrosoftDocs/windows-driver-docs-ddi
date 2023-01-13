---
UID: NF:wdm.MmAllocateMdlForIoSpace
title: MmAllocateMdlForIoSpace function (wdm.h)
description: The MmAllocateMdlForIoSpace routine allocates an MDL and initializes this MDL to describe a set of physical address ranges in I/O address space.
tech.root: kernel
ms.date: 01/10/2023
keywords: ["MmAllocateMdlForIoSpace function"]
ms.keywords: MmAllocateMdlForIoSpace, MmAllocateMdlForIoSpace routine [Kernel-Mode Driver Architecture], kernel.mmallocatemdlforiospace, wdm/MmAllocateMdlForIoSpace
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmAllocateMdlForIoSpace
 - wdm/MmAllocateMdlForIoSpace
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmAllocateMdlForIoSpace
---

## -description

The **MmAllocateMdlForIoSpace** routine allocates an [**MDL**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl) and initializes this MDL to describe a set of physical address ranges in I/O address space.

## -parameters

### -param PhysicalAddressList [in]

A pointer to an array of [**MM_PHYSICAL_ADDRESS_LIST**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_mm_physical_address_list) structures that describe the physical address ranges to include in the allocated MDL.

### -param NumberOfEntries [in]

The number of elements in the **MM_PHYSICAL_ADDRESS_LIST** array pointed to by *PhysicalAddressList*.

### -param NewMdl [out]

A pointer to a location to which the routine writes a pointer to the newly allocated MDL.

## -returns

**MmAllocateMdlForIoSpace** returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER_1** | A physical address is not aligned to a page boundary; or a physical address range is not a multiple of the page size; or a physical address range is used by the operating system for RAM and is not available for use as I/O space. |
| **STATUS_INSUFFICIENT_RESOURCES** | Insufficient system resources are available to perform the requested operation. |

Do not assume that the preceding list of error return codes is exhaustive. The routine might return error codes that do not appear in the list.

## -remarks

This routine accepts, as an input parameter, an array of **MM_PHYSICAL_ADDRESS_LIST** structures that describe a set of physical address ranges in I/O address space, and allocates an MDL that describes these ranges. Consecutive physical address ranges in the array are not required to be contiguous.

The physical address ranges in the *PhysicalAddressList* array must satisfy the following conditions:

- The base physical address for each range must be aligned to a PAGE_SIZE boundary in memory.

- The size, in bytes, of each range must be an integer multiple of PAGE_SIZE.

- All physical address ranges must be in memory that is available for use as I/O address space. They cannot be in memory space that is used by the operating system for RAM.

- The total size of all the ranges must be less than 4 gigabytes. Specifically, the total size must not exceed 2^32 - 1 bytes.

The caller is responsible for freeing the allocated MDL when it is no longer needed. To free the MDL, call the [IoFreeMdl](/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreemdl) routine. For more information about MDLs, see [Using MDLs](/windows-hardware/drivers/kernel/using-mdls).

The MDL that is created by **MmAllocateMdlForIoSpace** is not mapped to virtual memory, but can be supplied to a routine such as [MapTransferEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex) to initiate a DMA transfer to or from the physical memory ranges described by the MDL. To map this MDL to a contiguous range of virtual addresses so that it can be accessed by the processor, call the [MmMapLockedPagesSpecifyCache](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache) routine.

Only ranges of the physical address space that are not reserved by the operating system for use as memory are available to drivers for use as I/O address space. Drivers use I/O address space to access memory-mapped hardware resources such as device registers. When a driver starts, it might receive one or more physical address ranges as translated hardware resources. For more information, see [Mapping Bus-Relative Addresses to Virtual Addresses](/windows-hardware/drivers/kernel/mapping-bus-relative-addresses-to-virtual-addresses).

In some processor architectures, such as the x86, devices can be either memory-mapped or mapped to port addresses in a special  I/O address space that is dedicated to devices and is separate from the memory address space. Drivers can use **MmAllocateMdlForIoSpace** to allocate MDLs only for memory-mapped devices.

### Examples

The following code example shows how to construct an array of [**MM_PHYSICAL_ADDRESS_LIST**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_mm_physical_address_list) structures that describe the physical address ranges to include in the allocated MDL.

```cpp
extern ULONG64 BasePhysicalAddress;
extern SIZE_T ChunkSize;
extern SIZE_T Stride;

#define ARRAYSIZE(x)  (sizeof(x)/sizeof((x)[0]))
 
NTSTATUS Status;
PMDL Mdl;
MM_PHYSICAL_ADDRESS_LIST AddressList[3];
 
AddressList[0].PhysicalAddress.QuadPart = BasePhysicalAddress;
AddressList[0].NumberOfBytes = ChunkSize;
 
BasePhysicalAddress += Stride;
 
AddressList[1].PhysicalAddress.QuadPart = BasePhysicalAddress;
AddressList[1].NumberOfBytes = ChunkSize;
 
BasePhysicalAddress += Stride;
 
AddressList[2].PhysicalAddress.QuadPart = BasePhysicalAddress;
AddressList[2].NumberOfBytes = ChunkSize;
 
Status = MmAllocateMdlForIoSpace (AddressList, ARRAYSIZE(AddressList), &Mdl);
```

In this example, the starting physical address is specified by the `BasePhysicalAddress` variable. The number of bytes in each physical address range is specified by the `ChunkSize` variable. The byte offset from the start of one physical range to the start of the next is specified by the `Stride` variable. `BasePhysicalAddress` must be aligned to a page boundary in memory, and `ChunkSize` and `Stride` must be multiples of the page size.

## -see-also

[IoFreeMdl](/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreemdl)

[**MDL**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl)

[**MM_PHYSICAL_ADDRESS_LIST**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_mm_physical_address_list)

[MapTransferEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex)

[MmMapLockedPagesSpecifyCache](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache)
