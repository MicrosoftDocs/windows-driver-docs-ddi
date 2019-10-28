---
UID: NS:d3dkmddi._DXGKARG_MAPCPUHOSTAPERTURE
title: _DXGKARG_MAPCPUHOSTAPERTURE (d3dkmddi.h)
description: The DXGKARG_MAPCPUHOSTAPERTURE structure is used to map an allocation, resident in a local memory segment, into the CPU host aperture in order to make it visible to the CPU.
old-location: display\dxgkarg_mapcpuhostaperture.htm
ms.assetid: ACC0C800-B6E3-4EF2-846C-63BF4564D0FD
ms.date: 05/10/2018
ms.keywords: DXGKARG_MAPCPUHOSTAPERTURE, DXGKARG_MAPCPUHOSTAPERTURE structure [Display Devices], _DXGKARG_MAPCPUHOSTAPERTURE, d3dkmddi/DXGKARG_MAPCPUHOSTAPERTURE, display.dxgkarg_mapcpuhostaperture
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGKARG_MAPCPUHOSTAPERTURE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGKARG_MAPCPUHOSTAPERTURE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_MAPCPUHOSTAPERTURE
---

# _DXGKARG_MAPCPUHOSTAPERTURE structure


## -description


The <b>DXGKARG_MAPCPUHOSTAPERTURE</b> structure is used to map an allocation, resident in a local memory segment, into the CPU host aperture in order to make it visible to the CPU.


## -struct-fields




### -field hAllocation

Specifies the allocation handle, associated with the allocation being mapped. This is the handle, returned by the kernel mode driver from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> or passed in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_createcontextallocation">DxgkCbCreateContextAllocation</a>. This parameter will be <b>NULL</b> for implicit allocations, such as a page table.


### -field SegmentId

Specifies the segment identifier of the segment being accessed.


### -field PhysicalAdapterIndex

A zero-based physical adapter index in a linked display adapter link.
The page size is equal to the segment page size, reported in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentflags">DXGK_SEGMENTFLAGS</a>.


<div class="alert"><b>Note</b>  The allocation itself might be aligned on 4KB page boundary. When the segment page size is 64 KB, CPU host aperture in this case will map more than the allocation size.
</div>
<div> </div>

### -field NumberOfPages

Specifies the number of pages being mapped.


### -field pCpuHostAperturePages

Array of CPU Host Aperture pages to map. This is an array of page indices from the start of the CPU host aperture physical address.


### -field pMemorySegmentPages

MDL-style array of page indices to the allocation pages that need to be mapped into the CPU host aperture. The page indexes starting from 0. 

