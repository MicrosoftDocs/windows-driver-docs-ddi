---
UID: NF:wdm.MmAllocateMdlForIoSpace
title: MmAllocateMdlForIoSpace function (wdm.h)
description: The MmAllocateMdlForIoSpace routine allocates an MDL and initializes this MDL to describe a set of physical address ranges in I/O address space.
old-location: kernel\mmallocatemdlforiospace.htm
tech.root: kernel
ms.assetid: 198ECC2A-1AC0-44FA-8E5C-84F1C8BEE246
ms.date: 04/30/2018
keywords: ["MmAllocateMdlForIoSpace function"]
ms.keywords: MmAllocateMdlForIoSpace, MmAllocateMdlForIoSpace routine [Kernel-Mode Driver Architecture], kernel.mmallocatemdlforiospace, wdm/MmAllocateMdlForIoSpace
f1_keywords:
 - "wdm/MmAllocateMdlForIoSpace"
 - "MmAllocateMdlForIoSpace"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmAllocateMdlForIoSpace
targetos: Windows
req.typenames: 
---

# MmAllocateMdlForIoSpace function


## -description


The <b>MmAllocateMdlForIoSpace</b> routine allocates an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> and initializes this MDL to describe a set of physical address ranges in I/O address space.


## -parameters




### -param PhysicalAddressList [in]

A pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mm_physical_address_list">MM_PHYSICAL_ADDRESS_LIST</a> structures that describe the physical address ranges to include in the allocated MDL.


### -param NumberOfEntries [in]

The number of elements in the <b>MM_PHYSICAL_ADDRESS_LIST</b> array pointed to by <i>PhysicalAddressList</i>.


### -param NewMdl [out]

A pointer to a location to which the routine writes a pointer to the newly allocated MDL.


## -returns



<b>MmAllocateMdlForIoSpace</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
A physical address is not aligned to a page boundary; or a physical address range is not a multiple of the page size; or a physical address range is used by the operating system for RAM and is not available for use as I/O space.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient system resources are available to perform the requested operation.

</td>
</tr>
</table>
 

Do not assume that the preceding list of error return codes is exhaustive. The routine might return error codes that do not appear in the list.




## -remarks



This routine accepts, as an input parameter, an array of <b>MM_PHYSICAL_ADDRESS_LIST</b> structures that describe a set of physical address ranges in I/O address space, and allocates an MDL that describes these ranges. Consecutive physical address ranges in the array are not required to be contiguous.

The physical address ranges in the <i>PhysicalAddressList</i> array must satisfy the following conditions:

<ul>
<li>The base physical address for each range must be aligned to a PAGE_SIZE boundary in memory.</li>
<li>The size, in bytes, of each range must be an integer multiple of PAGE_SIZE.</li>
<li>All physical address ranges must be in memory that is available for use as I/O address space. They cannot be in memory space that is used by the operating system for RAM.</li>
<li>The total size of all the ranges must be less than 4 gigabytes. Specifically, the total size must not exceed 2³²-1 bytes.</li>
</ul>
The caller is responsible for freeing the allocated MDL when it is no longer needed. To free the MDL, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreemdl">IoFreeMdl</a> routine. For more information about MDLs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.

The MDL that is created by <b>MmAllocateMdlForIoSpace</b> is not mapped to virtual memory, but can be supplied to a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a> to initiate a DMA transfer to or from the physical memory ranges described by the MDL. To map this MDL to a contiguous range of virtual addresses so that it can be accessed by the processor, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a> routine.

Only ranges of the physical address space that are not reserved by the operating system for use as memory are available to drivers for use as I/O address space. Drivers use I/O address space to access memory-mapped hardware resources such as device registers. When a driver starts, it might receive one or more physical address ranges as translated hardware resources. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mapping-bus-relative-addresses-to-virtual-addresses">Mapping Bus-Relative Addresses to Virtual Addresses</a>.

In some processor architectures, such as the x86, devices can be either memory-mapped or mapped to port addresses in a special  I/O address space that is dedicated to devices and is separate from the memory address space. Drivers can use <b>MmAllocateMdlForIoSpace</b> to allocate MDLs only for memory-mapped devices.


#### Examples

The following code example shows how to construct an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mm_physical_address_list">MM_PHYSICAL_ADDRESS_LIST</a> structures that describe the physical address ranges to include in the allocated MDL.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>extern ULONG64 BasePhysicalAddress;
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
</pre>
</td>
</tr>
</table></span></div>
In this example, the starting physical address is specified by the <code>BasePhysicalAddress</code> variable. The number of bytes in each physical address range is specified by the <code>ChunkSize</code> variable. The byte offset from the start of one physical range to the start of the next is specified by the <code>Stride</code> variable. <code>BasePhysicalAddress</code> must be aligned to a page boundary in memory, and <code>ChunkSize</code> and <code>Stride</code> must be multiples of the page size.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreemdl">IoFreeMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mm_physical_address_list">MM_PHYSICAL_ADDRESS_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a>
 

 

