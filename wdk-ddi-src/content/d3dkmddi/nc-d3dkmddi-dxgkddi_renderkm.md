---
UID: NC:d3dkmddi.DXGKDDI_RENDERKM
title: DXGKDDI_RENDERKM (d3dkmddi.h)
description: For display adapters that support GDI hardware acceleration, the DxgkDdiRenderKm function generates a direct memory access (DMA) buffer from the command buffer that the kernel-mode Canonical Display Driver (CDD) passed.
old-location: display\dxgkddirenderkm.htm
ms.assetid: 5841934d-7e0a-4bb8-a7f8-17d8c0af351f
ms.date: 05/10/2018
keywords: ["DXGKDDI_RENDERKM callback function"]
ms.keywords: DXGKDDI_RENDERKM, DXGKDDI_RENDERKM callback, DmFunctions_f8138753-f755-410c-b0a0-4422dee9bfb6.xml, DxgkDdiRenderKm, DxgkDdiRenderKm callback function [Display Devices], d3dkmddi/DxgkDdiRenderKm, display.dxgkddirenderkm
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiRenderKm"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiRenderKm
product:
 - Windows
---

# DXGKDDI_RENDERKM callback function

## -description

For display adapters that support GDI hardware acceleration, the <i>DxgkDdiRenderKm</i> function generates a direct memory access (DMA) buffer from the command buffer that the kernel-mode Canonical Display Driver (CDD) passed.

## -parameters

### -param hContext

[in] A handle to the device context for the DMA and command buffers. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a> function previously returned this handle in the <b>hContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a> structure that the <i>pCreateContext</i> parameter of <i>DxgkDdiCreateContext</i> points to.

If the driver does not support context creation, the Microsoft DirectX graphics kernel subsystem replaces the handle to the context with a handle to the device. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a> function previously returned the device handle in the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a> structure that the <i>pCreateDevice</i> parameter of <i>DxgkDdiCreateDevice</i> points to.

### -param pRenderKmArgs

[in/out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a> structure that contains information about the DMA buffer and a formatted command buffer.

If the display miniport driver supports GDI hardware acceleration, <i>pRenderKmArgs</i>-><b>pCommand</b> points to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_renderkm_command">DXGK_RENDERKM_COMMAND</a> command buffer.

The driver must translate the input command buffer into DMA buffer commands and build the patch location list.

## -returns

<i>DxgkDdiRenderKm</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The entire command buffer was translated. | 
| **STATUS_NO_MEMORY** | [DxgkDdiRenderKm](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm)  could not allocate memory that was required for it to complete. | 
| **STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER** | The current DMA buffer is depleted. | 
| **STATUS_INVALID_PARAMETER** | [DxgkDdiRenderKm](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm)  detected instruction parameters that graphics hardware could not support; however, the graphics hardware can support the instructions themselves. The driver is not required to return this error code. Instead, it can return STATUS_ILLEGAL_INSTRUCTION when it detects unsupported instruction parameters. | 
| **STATUS_INVALID_USER_BUFFER** | [DxgkDdiRenderKm](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm)  detected data or instruction underrun or overrun. That is, the driver received less or more instructions or data than expected. The driver is not required to return this error code. Instead, it can return STATUS_ILLEGAL_INSTRUCTION when it detects data or instruction underrun or overrun. | 
| **STATUS_INVALID_HANDLE** | [DxgkDdiRenderKm](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm)  detected an invalid handle in the command buffer. | 
| **STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE** | The display miniport driver detected an error in the DMA stream. The graphics context device is placed in a lost state if the driver returns this error code. |

## -remarks

The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiRenderKm</i> function to generate a DMA buffer from the command buffer that is passed by the kernel-mode Canonical Display Driver (CDD) provided by the operating system. In addition to the output DMA buffer, the display miniport driver should also generate a list of output patch locations. The video memory manager uses this list to split and patch DMA buffers appropriately.

<div class="alert"><b>Note</b>    Access to the kernel buffers does not require protection from <code>try/except</code> code. </div>
<div> </div>
The display miniport driver is not required to use information that the CDD provides if it can re-create the information more optimally. For example, if the <i>pRender</i>-><b>pPatchLocationListIn</b> member is empty because the user-mode display driver did not provide an input patch-location list, the display miniport driver can generate the content of the <i>pRender</i>-><b>pPatchLocationListOut</b> member based on the content of the command buffer instead.

In addition to the device-specific handle, the DirectX graphics kernel subsystem provides the display miniport driver with the last known GPU segment address for each allocation. If allocation index <i>N</i> is currently paged out, the DirectX graphics kernel subsystem sets the <b>SegmentId</b> member of the <i>N</i>th element of the <b>pAllocationList</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a> to zero. If the <b>SegmentId</b> member of the <i>N</i>th element of the allocation list is not set to zero, the display miniport driver must patch the generated DMA buffer with the provided segment address information before the DirectX graphics kernel subsystem calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_patch">DxgkDdiPatch</a> function to repatch the DMA buffer. The driver must perform this initial patching when requested because the DirectX graphics kernel subsystem might not call the <i>DxgkDdiPatch</i> function on a DMA buffer that the driver should have properly patched.

<div class="alert"><b>Note</b>    Even though the driver's <i>DxgkDdiRenderKm</i> function performs the initial DMA buffer patching as described earlier, the driver must still insert all the references to allocations into the output patch-location list that the <b>pPatchLocationListOut</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a> specifies. This list must contain all of the references because the addresses of the allocations might change before the DMA buffer is submitted to the GPU; therefore, the DirectX graphics kernel subsystem will call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_patch">DxgkDdiPatch</a> function to repatch the DMA buffer. </div>
<div> </div>
To unbind an allocation, the display miniport driver can specify an element in the allocation list that references a <b>NULL</b> handle and then can use a patch-location element that references that <b>NULL</b> allocation. Typically, the driver should use the first element of the allocation list (element 0) as the <b>NULL</b> element.

In guaranteed contract DMA mode, when the display miniport driver translates a command buffer to a DMA buffer, the CDD must guarantee enough resources for the translation command. If enough resources do not exist for the translation, the display miniport driver must reject the DMA buffer. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/using-the-guaranteed-contract-dma-buffer-model">Using the Guaranteed Contract DMA Buffer Model</a>.

<i>DxgkDdiRenderKm</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_renderkm_command">DXGK_RENDERKM_COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_openallocationinfo">DxgkDdiOpenAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_patch">DxgkDdiPatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a>

