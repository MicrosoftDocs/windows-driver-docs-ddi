---
UID: NC:d3dkmddi.DXGKDDI_RENDERKM
title: DXGKDDI_RENDERKM (d3dkmddi.h)
description: Learn more about the DxgkDdiRenderKm function.
ms.date: 06/09/2023
keywords: ["DXGKDDI_RENDERKM callback function"]
ms.keywords: DXGKDDI_RENDERKM, DXGKDDI_RENDERKM callback, DmFunctions_f8138753-f755-410c-b0a0-4422dee9bfb6.xml, DxgkDdiRenderKm, DxgkDdiRenderKm callback function [Display Devices], d3dkmddi/DxgkDdiRenderKm, display.dxgkddirenderkm
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 7
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
 - DXGKDDI_RENDERKM
 - d3dkmddi/DXGKDDI_RENDERKM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_RENDERKM
product:
 - Windows
---

# DXGKDDI_RENDERKM callback function

## -description

For display adapters that support GDI hardware acceleration, the **DxgkDdiRenderKm** function generates a direct memory access (DMA) buffer from the command buffer that the kernel-mode Canonical Display Driver (CDD) passed.

## -parameters

### -param hContext [in]

A handle to the device context for the DMA and command buffers. The display miniport driver's [**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md) function previously returned this handle in the **hContext** member of the [**DXGKARG_CREATECONTEXT**](ns-d3dkmddi-_dxgkarg_createcontext.md) structure that the **pCreateContext** parameter of **DxgkDdiCreateContext** points to.

If the driver does not support context creation, the Microsoft DirectX graphics kernel subsystem replaces the handle to the context with a handle to the device. The display miniport driver's [**DxgkDdiCreateDevice**](nc-d3dkmddi-dxgkddi_createdevice.md) function previously returned the device handle in the **hDevice** member of the [**DXGKARG_CREATEDEVICE**](ns-d3dkmddi-_dxgkarg_createdevice.md) structure that the **pCreateDevice** parameter of **DxgkDdiCreateDevice** points to.

### -param pRenderKmArgs [in/out]

A pointer to a [**DXGKARG_RENDER**](ns-d3dkmddi-_dxgkarg_render.md) structure that contains information about the DMA buffer and a formatted command buffer.

If the display miniport driver supports GDI hardware acceleration, **pRenderKmArgs**->**pCommand** points to the [**DXGK_RENDERKM_COMMAND**](ns-d3dkmddi-_dxgk_renderkm_command.md) command buffer.

The driver must translate the input command buffer into DMA buffer commands and build the patch location list.

## -returns

**DxgkDdiRenderKm** returns one of the following values:

| **Return code** | **Description** |
|:--|:--|
| **STATUS_SUCCESS** | The entire command buffer was translated. |
| **STATUS_NO_MEMORY** | **DxgkDdiRenderKm**  could not allocate memory that was required for it to complete. |
| **STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER** | The current DMA buffer is depleted. |
| **STATUS_INVALID_PARAMETER** | **DxgkDdiRenderKm**  detected instruction parameters that graphics hardware could not support; however, the graphics hardware can support the instructions themselves. The driver is not required to return this error code. Instead, it can return STATUS_ILLEGAL_INSTRUCTION when it detects unsupported instruction parameters. |
| **STATUS_INVALID_USER_BUFFER** | **DxgkDdiRenderKm**  detected data or instruction underrun or overrun. That is, the driver received less or more instructions or data than expected. The driver is not required to return this error code. Instead, it can return STATUS_ILLEGAL_INSTRUCTION when it detects data or instruction underrun or overrun. |
| **STATUS_INVALID_HANDLE** | **DxgkDdiRenderKm**  detected an invalid handle in the command buffer. |
| **STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE** | The display miniport driver detected an error in the DMA stream. The graphics context device is placed in a lost state if the driver returns this error code. |

## -remarks

The DirectX graphics kernel subsystem calls the display miniport driver's **DxgkDdiRenderKm** function to generate a DMA buffer from the command buffer that is passed by the kernel-mode Canonical Display Driver (CDD) provided by the operating system. In addition to the output DMA buffer, the display miniport driver should also generate a list of output patch locations. The video memory manager uses this list to split and patch DMA buffers appropriately.

Access to the kernel buffers does not require protection from ```try/except``` code.

The display miniport driver is not required to use information that the CDD provides if it can re-create the information more optimally. For example, if the **pRender**->**pPatchLocationListIn** member is empty because the user-mode display driver did not provide an input patch-location list, the display miniport driver can generate the content of the **pRender**->**pPatchLocationListOut** member based on the content of the command buffer instead.

In addition to the device-specific handle, the DirectX graphics kernel subsystem provides the display miniport driver with the last known GPU segment address for each allocation. If allocation index **N** is currently paged out, the DirectX graphics kernel subsystem sets the **SegmentId** member of the **N**th element of the **pAllocationList** member of [**DXGKARG_RENDER**](ns-d3dkmddi-_dxgkarg_render.md) to zero. If the **SegmentId** member of the **N**th element of the allocation list is not set to zero, the display miniport driver must patch the generated DMA buffer with the provided segment address information before the DirectX graphics kernel subsystem calls the [**DxgkDdiPatch**](nc-d3dkmddi-dxgkddi_patch.md) function to repatch the DMA buffer. The driver must perform this initial patching when requested because the DirectX graphics kernel subsystem might not call the **DxgkDdiPatch** function on a DMA buffer that the driver should have properly patched.

Even though the driver's **DxgkDdiRenderKm** function performs the initial DMA buffer patching as described earlier, the driver must still insert all the references to allocations into the output patch-location list that the **pPatchLocationListOut** member of [**DXGKARG_RENDER**](ns-d3dkmddi-_dxgkarg_render.md) specifies. This list must contain all of the references because the addresses of the allocations might change before the DMA buffer is submitted to the GPU; therefore, the DirectX graphics kernel subsystem will call the [**DxgkDdiPatch**](nc-d3dkmddi-dxgkddi_patch.md) function to repatch the DMA buffer.

To unbind an allocation, the display miniport driver can specify an element in the allocation list that references a **NULL** handle and then can use a patch-location element that references that **NULL** allocation. Typically, the driver should use the first element of the allocation list (element 0) as the **NULL** element.

In guaranteed contract DMA mode, when the display miniport driver translates a command buffer to a DMA buffer, the CDD must guarantee enough resources for the translation command. If enough resources do not exist for the translation, the display miniport driver must reject the DMA buffer. For more information, see [Using the Guaranteed Contract DMA Buffer Model](/windows-hardware/drivers/display/using-the-guaranteed-contract-dma-buffer-model).

**DxgkDdiRenderKm** should be made pageable.

## -see-also

[**D3DDDI_ALLOCATIONLIST**](../d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist.md)

[**DXGKARG_CREATECONTEXT**](ns-d3dkmddi-_dxgkarg_createcontext.md)

[**DXGKARG_CREATEDEVICE**](ns-d3dkmddi-_dxgkarg_createdevice.md)

[**DXGK_ALLOCATIONLIST**](ns-d3dkmddi-_dxgk_allocationlist.md)

[**DXGK_RENDERKM_COMMAND**](ns-d3dkmddi-_dxgk_renderkm_command.md)

[**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md)

[**DxgkDdiCreateDevice**](nc-d3dkmddi-dxgkddi_createdevice.md)

[**DxgkDdiOpenAllocation**](nc-d3dkmddi-dxgkddi_openallocationinfo.md)

[**DxgkDdiPatch**](nc-d3dkmddi-dxgkddi_patch.md)

[**DxgkDdiRender**](nc-d3dkmddi-dxgkddi_render.md)
