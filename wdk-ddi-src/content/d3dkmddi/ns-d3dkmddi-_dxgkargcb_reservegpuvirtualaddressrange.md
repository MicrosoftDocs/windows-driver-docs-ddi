---
UID: NS:d3dkmddi._DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
title: _DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE (d3dkmddi.h)
description: DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE is used with the DxgkCbReserveGpuVirtualAddressRangedevice driver interface (DDI) to allow the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process.
old-location: display\dxgkargcb_reservegpuvirtualaddressrange.htm
ms.assetid: D555E595-4319-4FCC-84A7-52FA3F278FFD
ms.date: 05/10/2018
keywords: ["DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE structure"]
ms.keywords: DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE structure [Display Devices], _DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, *INOUT_PDXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, d3dkmddi/DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE, display.dxgkargcb_reservegpuvirtualaddressrange
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
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
f1_keywords:
 - _DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
 - d3dkmddi/_DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
 - DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
 - d3dkmddi/DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE
---

# _DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE structure


## -description

<b>DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE</b> is used with the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange">DxgkCbReserveGpuVirtualAddressRange</a>device driver interface (DDI) to allow the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process.

## -struct-fields

### -field hDxgkProcess

The handle that was passed to <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createprocess">DxgkDdiCreateProcess</a>.

### -field SizeInBytes

The size of the address range in bytes, this must be set to an integral multiple of the address space covered by a single page table entry.

### -field Alignment

The number of bytes to align the start address to. Must be a multiple of the address space covered by a single page table entry and a power of 2.

### -field StartVirtualAddress

The starting location of the reserved address range.

### -field BaseAddress

The base virtual address of the virtual address range in bytes. It must be aligned to the size of the address space, covered by a single page table entry.

### -field AllowUserModeMapping

Allow the user mode driver to map allocations to the range.

### -field Flags

A single value containing the flags set in the structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange">DxgkCbReserveGpuVirtualAddressRange</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createprocess">DxgkDdiCreateProcess</a>