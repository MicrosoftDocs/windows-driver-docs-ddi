---
UID: NS:d3dkmddi._DXGKARG_RENDER
title: _DXGKARG_RENDER (d3dkmddi.h)
description: The DXGKARG_RENDER structure describes members for generating a direct memory access (DMA) buffer from a command buffer.
old-location: display\dxgkarg_render.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_RENDER structure"]
ms.keywords: "*INOUT_PDXGKARG_RENDER, DXGKARG_RENDER, DXGKARG_RENDER structure [Display Devices], DmStructs_a297ffab-b45d-4c92-820c-0ef11849445e.xml, _DXGKARG_RENDER, d3dkmddi/DXGKARG_RENDER, display.dxgkarg_render"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: DXGKARG_RENDER
f1_keywords:
 - _DXGKARG_RENDER
 - d3dkmddi/_DXGKARG_RENDER
 - DXGKARG_RENDER
 - d3dkmddi/DXGKARG_RENDER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_RENDER
 - DXGKARG_RENDER
---

# _DXGKARG_RENDER structure


## -description

The DXGKARG_RENDER structure describes members for generating a direct memory access (DMA) buffer from a command buffer.

## -struct-fields

### -field pCommand

[in] A pointer to the start of the command buffer.

<div class="alert"><b>Note</b>  When <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a> is called, the display miniport driver must validate the buffer. See Remarks in <b>DxgkDdiRender</b> for important info on how the driver should access this member.</div>
<div> </div>

### -field CommandLength

[in] The size, in bytes, of the command buffer that <b>pCommand</b> points to.

### -field pDmaBuffer

[out] A pointer to the start of the DMA buffer, which is aligned on 4 KB. This buffer can be sent through DMA to the graphics hardware. Before the display miniport driver returns from the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a> or <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a> functions, the driver should set <b>pDmaBuffer</b> to the next empty byte that follows the last byte that the driver wrote to, or the driver should point to the location (one byte beyond the buffer space) if no more space is available. This location would have been correct if the buffer was large enough.

### -field DmaSize

[in] The size, in bytes, of the DMA buffer that <b>pDmaBuffer</b> points to.

### -field pDmaBufferPrivateData

[in] A pointer to a driver-resident private data structure that is used for generating the DMA buffer that <b>pDmaBuffer</b> points to.

### -field DmaBufferPrivateDataSize

[in] The number of bytes that remain in the private data structure that <b>pDmaBufferPrivateData</b> points to for the current operation.

### -field pAllocationList

[in] An array of <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a> structures for the list of allocations that the DMA buffer references. Each allocation that is referenced should appear once for optimal performance.

### -field AllocationListSize

[in] The available number of elements in the array that <b>pAllocationList</b> specifies, which represents the number of allocation specifications to send through DMA to the graphics hardware.

### -field pPatchLocationListIn

[in] An array of <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a> structures for the patch-location list that the user-mode display driver provides in a call to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a> function.

<div class="alert"><b>Note</b>  When <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a> is called, the display miniport driver must validate the buffer. See Remarks in <b>DxgkDdiRender</b> for important info on how the driver should access this member.</div>
<div> </div>

### -field PatchLocationListInSize

[in] The number of elements in the patch-location list that <b>pPatchLocationListIn</b> specifies.

### -field pPatchLocationListOut

[in/out] An array of <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a> structures for the patch-location list that the display miniport driver fills in. Before the driver returns from a call to its <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a> or <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a> functions, the driver must set <b>pPatchLocationListOut</b> to the next <b>D3DDDI_PATCHLOCATIONLIST</b> element that follows the last <b>D3DDDI_PATCHLOCATIONLIST</b> element that the driver updated.

### -field PatchLocationListOutSize

[in] The number of elements in the patch-location list that <b>pPatchLocationListOut</b> specifies. The display miniport driver is not required to fill all of the elements in the entire list; the driver must use only elements that are necessary to describe the patch location within the DMA buffer.

### -field MultipassOffset

[in/out] A UINT value that specifies the progress of the rendering operation if the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a> or <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a> functions must return <b>STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER</b> to obtain a new DMA buffer. When the driver's <i>DxgkDdiRender</i> or <i>DxgkDdiRenderKm</i> function is first called with a new command buffer, <b>MultipassOffset</b> is initialized to zero. Before the driver returns from the <i>DxgkDdiRender</i> or <i>DxgkDdiRenderKm</i> calls, the driver sets this member to show translation progress for subsequent <i>DxgkDdiRender</i> or <i>DxgkDdiRenderKm</i> call with the same command buffer. The DirectX graphics kernel subsystem does not change the value further.

### -field DmaBufferSegmentId

[in] The identifier of the memory segment that the DMA buffer was paged in. If the identifier is zero, the DMA buffer is not correctly paged in.

### -field DmaBufferPhysicalAddress

[in] A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address where the DMA buffer was paged in. If the physical address is zero, the DMA buffer is not correctly paged in.

## -remarks

    Support for the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a> function is added beginning with Windows 7 for display adapters that support <a href="/windows-hardware/drivers/display/gdi-hardware-acceleration">GDI Hardware Acceleration</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>

