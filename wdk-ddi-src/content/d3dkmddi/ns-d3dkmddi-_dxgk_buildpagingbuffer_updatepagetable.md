---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE
title: "_DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE"
author: windows-driver-content
description: DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE is used as part of a page table update operation.
old-location: display\dxgk_buildpagingbuffer_updatepagetable.htm
ms.assetid: 734B2E28-75F8-49AE-AAAB-EB0C037C6432
ms.date: 05/10/2018
ms.keywords: DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE, DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE, d3dkmddi/DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE, display.dxgk_buildpagingbuffer_updatepagetable
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE
---

# _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE structure


## -description


<b>DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE</b> is used as part of a page table update operation.


## -struct-fields




### -field PageTableLevel

Level of a page table, which is updated.


### -field hAllocation

Kernel mode driver handle of an allocation, which is mapped by the page table entries. The handle is returned by the kernel mode driver from <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>. The handle can be <b>NULL</b> for allocations, which do not have a kernel mode drver   handle (page tables, page directories, etc.).


### -field PageTableAddress

Address of the page table to update. If <b>DXGK_VIRTUALADDRESSCAPS:: PageTableUpdateMode</b> is <b>DXGK_PAGETABLEUPDATE_CPU_VIRTUAL</b>, the CPU virtual address is in the <b>CpuVirtual</b> field. If <b>DXGK_VIRTUALADDRESSCAPS:: PageTableUpdateMode</b> is <b>DXGK_PAGETABLEUPDATE_GPU_VIRTUAL</b>, the GPU virtual address is in the <b>GpuVirtual</b> field. If <b>DXGK_VIRTUALADDRESSCAPS:: PageTableUpdateMode</b> is <b>DXGK_PAGETABLEUPDATE_GPU_PHYSICAL</b>, the GPU physical address is in the <b>GpuPhysical</b> field.


### -field pPageTableEntries

The entries which need to be copied. The index zero in the <b>pPageTableEntries</b> array corresponds to the <b>StartIndex</b> in the driver page table entry array.


### -field StartIndex

The starting index of a page table entry within the page table where the entries should be copied. The page table entry array index is zero-based.


### -field NumPageTableEntries

The number of entries which need to be copied.


### -field Reserved0

This member is reserved and should be set to zero.


### -field Flags


<a href="https://msdn.microsoft.com/library/windows/hardware/dn914482">DXGK_UPDATEPAGETABLEFLAGS</a> structure describing the update operation.


### -field DriverProtection

Passed by UMD in MapGpuVirtualAddressRangeCb.


### -field AllocationOffsetInBytes

When <b>hAllocation</b> is non-NULL, this field specifies the relative offset, in bytes, from the beginning of the allocation to the first page being targeted by this update operation. If the update target multiple pages from <b>hAllocation</b>, those pages are guaranteed to be sequential. For example, video memory manager may be updating a GPU virtual address to page 4,5,6,7 in <b>hAllocation</b>. There will never be a case where a driver would see a single update operation which target non sequential pages (ex. 4,5,7). Note that although the pages are guaranteed to be sequential from the point of view of the allocation, they may not be physically contiguous in memory.


### -field hProcess

Kernel mode driver process handle for the process whose page table entries are updated. This is the value returned from <a href="https://msdn.microsoft.com/E5AAEEB1-C29E-4AA7-9F8E-2C2DCFADED81">DxgkDdiCreateProcess</a>.


### -field UpdateMode

Defines the meaning of <b>PageTableAddress</b>. When initializing page tables for the paging process, the update mode is always <b>DXGK_PAGETABLEUPDATE_CPU_VIRTUAL</b> and <b>pDmaBuffer</b> is set to <b>NULL</b>. In this case the driver must update page tables immediately. In other cases the <b>UpdateMode</b> is set to the value, which is specified in <b>DXGK_VIRTUALADDRESSCAPS::GpuMmu.PageTableUpdateMode</b>.

When updating page table entries for a leaf page table, video memory manager assumes that each entry covers a 4KB page. If a GPU page is bigger (4 KB * 2n), the video memory manager will provide entries in the array, which point within GPU pages. The kernel mode driver might only need to initialize page table entries, which point to the beginning of GPU pages. The following figure illustrates this for the case when GPU page is 16 KB.


### -field pPageTableEntries64KB

The entries which need to be copied from the 64KB page tables. The index zero in the <b>pPageTableEntries</b> array corresponds to the <b>StartIndex</b> in the driver page table entry array. The array should be use only when the <b>DXGK_GPUMMUCAPS::DualPteSupported</b> cap is set.


### -field FirstPteVirtualAddress

The GPU virtual address that is mapped by the first updated page table entry.

