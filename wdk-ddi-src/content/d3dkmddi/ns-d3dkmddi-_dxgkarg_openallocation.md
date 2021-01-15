---
UID: NS:d3dkmddi._DXGKARG_OPENALLOCATION
title: _DXGKARG_OPENALLOCATION (d3dkmddi.h)
description: The DXGKARG_OPENALLOCATION structure describes allocations that the display miniport driver should open.
old-location: display\dxgkarg_openallocation.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_OPENALLOCATION structure"]
ms.keywords: DXGKARG_OPENALLOCATION, DXGKARG_OPENALLOCATION structure [Display Devices], DmStructs_442924a2-c130-487c-acdb-62a2b6e9f219.xml, _DXGKARG_OPENALLOCATION, d3dkmddi/DXGKARG_OPENALLOCATION, display.dxgkarg_openallocation
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available beginning with Windows Vista.
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
targetos: Windows
tech.root: display
req.typenames: DXGKARG_OPENALLOCATION
f1_keywords:
 - _DXGKARG_OPENALLOCATION
 - d3dkmddi/_DXGKARG_OPENALLOCATION
 - DXGKARG_OPENALLOCATION
 - d3dkmddi/DXGKARG_OPENALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_OPENALLOCATION
 - DXGKARG_OPENALLOCATION
---

# _DXGKARG_OPENALLOCATION structure


## -description

The DXGKARG_OPENALLOCATION structure describes allocations that the display miniport driver should open.

## -struct-fields

### -field NumAllocations

[in] The number of elements in the array that the <b>pOpenAllocation</b> member specifies, which represents the number of device-specific allocations to open.

### -field pOpenAllocation

[in/out] An array of <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_openallocationinfo">DXGK_OPENALLOCATIONINFO</a> structures for the allocations to open.

### -field pPrivateDriverData

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver. This block of private data is the same resource-specific data that is passed in the <b>pPrivateDriverData</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a> structure in the call to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> function. The display miniport driver cannot modify this block of private data.

### -field PrivateDriverSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.

### -field Flags

[in] A <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_openallocationflags">DXGK_OPENALLOCATIONFLAGS</a> structure that identifies the operation to perform for allocations.

### -field SubresourceIndex

[in] Supported beginning with Windows 8.

An index into the resource for the render target surface.

The operating system specifies this member only if the display miniport driver supports <a href="/windows-hardware/drivers/display/gdi-hardware-acceleration">GDI Hardware Acceleration</a>. Specifically, the display miniport driver must implement  the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a> function and must create the device with the <b>GdiDevice</b> member set in <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a>.<b>Flags</b>.

If the value of <b>SubresourceIndex</b> is greater than the number of subresources in the allocation, the display miniport driver should return an error.

### -field SubresourceOffset

[out] Supported beginning with Windows 8.

The offset, in bytes, from the start of the allocation to the start of the subresource.

### -field Pitch

[out] Supported beginning with Windows 8.

The pitch, in bytes, of the allocation—that is, the distance, in bytes, to the start of the next row.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_openallocationflags">DXGK_OPENALLOCATIONFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_openallocationinfo">DXGK_OPENALLOCATIONINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_openallocationinfo">DxgkDdiOpenAllocation</a>

