---
UID: NS:d3dukmdt._DXGK_PTE
title: _DXGK_PTE (d3dukmdt.h)
description: A page table entry (PTE) provides a physical address of a page and other attributes. The exact format of PTE depends on hardware implementation.
old-location: display\dxgk_pte.htm
tech.root: display
ms.assetid: 2d5c1f3e-69a6-4f7f-9c99-bbaf94e6401b
ms.date: 05/10/2018
ms.keywords: DXGK_PTE, DXGK_PTE structure [Display Devices], DmStructs_701e980c-29dc-46d2-8f03-ce8485a4cc70.xml, _DXGK_PTE, d3dukmdt/DXGK_PTE, display.dxgk_pte
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dukmdt.h
api_name:
- DXGK_PTE
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# _DXGK_PTE structure


## -description


A page table entry (PTE) provides a physical address of a page and other attributes. The exact format of PTE depends on hardware implementation. 


## -struct-fields




### -field Valid

When set, this indicates that the entry is valid. Accessing an invalid entry leads to an unrecoverable address fault, unless the <b>Zero</b> flag is set.


### -field Zero

When set with <b>Valid</b> = 1, the access to the entry lead to returning the zero value for the memory access. This is used to support tiled resources.

Supported starting with Windows 10.


### -field CacheCoherent

When set, this indicates that the memory page is cache coherent between CPU and GPU.


### -field ReadOnly

When set, this indicates that the memory page is read only.


### -field NoExecute

When set, this  indicates that the memory page contains data, which should not be treated as executable commands.

Supported starting with Windows 10.


### -field Segment

A zero-based GPU memory segment identifier where the corresponding memory page is located. The segment zero is reserved for system memory. 


### -field LargePage

The bit can be set only when the kernel mode driver sets the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562869">DXGK_VIRTUALADDRESSCAPS</a>::<b>GpuMmu</b>.<b>LargePageSupported</b> cap. When set the page table address (<b>PageTableAddress</b> + <b>SegmentId</b>) is the memory address of an allocation. The allocation size is equal to the virtual address range, covered by the lower page table level. This flag cannot be set for the leaf page tables.

Supported starting with Windows 10.


### -field PhysicalAdapterIndex

Defines a physical adapter index in a linked display adapter configuration. PTEs of page tables on one physical adapter can point to memory on another physical adapter.

Supported starting with Windows 10.


### -field PageTablePageSize

For the level 1 page table entry defines the pages size of the leaf page table PTEs. The value is provided by the  <a href="https://msdn.microsoft.com/library/windows/hardware/dn906834">DXGK_PTE_PAGE_SIZE</a> enumerator. This value should be ignored  when dual-PTE is supported.

Supported starting with Windows 10.


### -field SystemReserved0

 


### -field Reserved

Reserved for system use and will be set to zero.


### -field Flags

The unmasked value of the structure.


### -field PageAddress

The high 52 bits of the 64 bit physical address of a memory page. The low 12 bits are zero. The address is an offset from the start of the segment, defined by <b>Segment</b>, or a system memory address.


### -field PageTableAddress

The high 52 bits of the 64 bit physical address of a lower level page table. The low 12 bits are zero. The address is an offset from the start of the segment, defined by <b>Segment</b>, or a system memory address.

Supported starting with Windows 10.

