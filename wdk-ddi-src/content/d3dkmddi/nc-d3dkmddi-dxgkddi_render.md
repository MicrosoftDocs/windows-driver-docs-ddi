---
UID: NC:d3dkmddi.DXGKDDI_RENDER
title: DXGKDDI_RENDER (d3dkmddi.h)
description: The DxgkDdiRender function generates a direct memory access (DMA) buffer from the command buffer that the user-mode display driver passed.
old-location: display\dxgkddirender.htm
ms.assetid: fd634768-5e1e-4f40-82fd-5ef69148c3d7
ms.date: 05/10/2018
ms.keywords: DXGKDDI_RENDER, DXGKDDI_RENDER callback, DmFunctions_e6f475cd-e097-4ea7-9f66-9e0b2d78d46b.xml, DxgkDdiRender, DxgkDdiRender callback function [Display Devices], d3dkmddi/DxgkDdiRender, display.dxgkddirender
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiRender"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiRender
product:
 - Windows
---

# DXGKDDI_RENDER callback function

## -description

The <i>DxgkDdiRender</i> function generates a direct memory access (DMA) buffer from the command buffer that the user-mode display driver passed.

## -parameters

### -param hContext

[in] A handle to the device context for the DMA and command buffers. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a> function previously returned this handle in the <b>hContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a> structure that the <i>pCreateContext</i> parameter of <i>DxgkDdiCreateContext </i>points to. 

If the driver does not support context creation, the Microsoft DirectX graphics kernel subsystem replaces the handle to the context with a handle to the device. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a> function previously returned the device handle in the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a> structure that the <i>pCreateDevice</i> parameter of <i>DxgkDdiCreateDevice </i>points to.

### -param pRender

[in/out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a> structure that contains information about the DMA and command buffers.

## -returns

<i>DxgkDdiRender</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The entire command buffer was translated.|
|STATUS_NO_MEMORY|DxgkDdiRender could not allocate memory that was required for it to complete.|
|STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER|The current DMA buffer is depleted.|
|STATUS_PRIVILEGED_INSTRUCTION|DxgkDdiRender detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current central processing unit [CPU] process).|
|STATUS_ILLEGAL_INSTRUCTION|DxgkDdiRender detected instructions that graphics hardware could not support.|
|STATUS_INVALID_PARAMETER|DxgkDdiRender detected instruction parameters that graphics hardware could not support; however, the graphics hardware can support the instructions themselves. The driver is not required to return this error code. Instead, it can return STATUS_ILLEGAL_INSTRUCTION when it detects unsupported instruction parameters.|
|STATUS_INVALID_USER_BUFFER|DxgkDdiRender detected data or instruction underrun or overrun. That is, the driver received less or more instructions or data than expected. The driver is not required to return this error code. Instead, it can return STATUS_ILLEGAL_INSTRUCTION when it detects data or instruction underrun or overrun.|
|STATUS_INVALID_HANDLE|DxgkDdiRender detected an invalid handle in the command buffer.|
|STATUS_GRAPHICS_DRIVER_MISMATCH|The display miniport driver is not compatible with the user-mode display driver that initiated the call to DxgkDdiRender (that is, submitted the command buffer).|
|STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE|The display miniport driver detected an error in the DMA stream. The graphics context device is placed in a lost state if the driver returns this error code.|

## -remarks

The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiRender</i> function to generate a DMA buffer from the command buffer that the user-mode display driver passed. When the display miniport driver translates from the command buffer to the DMA buffer, the driver should also validate the command buffer to ensure that the command buffer does not contain any privileged commands or commands that can be used to access memory that does not belong to the process. In addition to the output DMA buffer, the display miniport driver should also generate a list of output patch locations. The video memory manager uses this list to split and patch DMA buffers appropriately. 

Both the command buffer <b>pCommand</b> and the input patch-location list <b>pPatchLocationListIn</b> that the user-mode display driver generates are allocated from the user-mode address space and are passed to the display miniport driver untouched. The display miniport driver must use <code>__try/__except</code> code on any access to the buffer and list and must validate the content of the buffer and list before copying the content to the respective kernel buffers (that is, before copying the content of the <b>pCommand</b> member to the <b>pDmaBuffer</b> member and the content of the <b>pPatchLocationListIn</b> member to the <b>pPatchLocationListOut</b> member, which are all members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a> structure that the <i>pRender</i> parameter points to).

Here's an example of how display miniport drivers should access these buffers using  <code>__try</code> and <code>__except</code> logic. <b>AllocationListIn</b> points to the user-mode buffer.

```cpp
__try
  {
    for (Index = 0; Index < AllocationListInSize; AllocationTable++, 
           AllocationListIn++, AllocationListOut++, Index++) 
    {
      D3DKMT_HANDLE AllocationHandle = AllocationListIn->hAllocation;
      . . .
    }
  }
__except(EXCEPTION_EXECUTE_HANDLER)
  {
    Status = STATUS_INVALID_PARAMETER;
    SAMPLE_LOG_ERROR(
  "Exception occurred accessing user-mode allocation list. Returning Status=0x%I64x",
      Status);
    goto cleanup;
  }
```

> [!NOTE]
> Access to the kernel buffers does not require protection from `try/except` code.

The display miniport driver is not required to use information that the user-mode display driver provides if recreating the information is more optimal. For example, if <b>pPatchLocationListIn</b> is empty because the user-mode display driver did not provide an input patch-location list, the display miniport driver can generate the content of <b>pPatchLocationListOut</b> based on the content of the command buffer instead.

The allocation list that the user-mode display driver provides is validated, copied, and converted into a kernel-mode allocation list during the kernel transition. The DirectX graphics kernel subsystem converts each <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a> element into a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a> element by converting the D3DKMT_HANDLE-typed handle that the user-mode display driver provides into a device-specific handle, which the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_openallocationinfo">DxgkDdiOpenAllocation</a> function returns. The index of each allocation and the write status of the allocation (that is, the setting of the <b>WriteOperation</b> bit-field flag) remains constant during the conversion. 

In addition to the device-specific handle, the DirectX graphics kernel subsystem provides the display miniport driver with the last known GPU segment address for each allocation. If allocation index <i>N</i> is currently paged out, the DirectX graphics kernel subsystem sets the <b>SegmentId</b> member of the <i>N</i>th element of the <b>pAllocationList</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a> to zero. If the <b>SegmentId</b> member of the <i>N</i>th element of the allocation list is not set to zero, the display miniport driver must pre-patch the generated DMA buffer with the provided segment address information. The driver must pre-patch when requested because the DirectX graphics kernel subsystem might not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_patch">DxgkDdiPatch</a> function on a DMA buffer that the driver should have properly pre-patched. 

> [!NOTE]
> Even though the driver's <i>DxgkDdiRender</i> function pre-patches the DMA buffer, the driver must still insert all of the references to allocations into the output patch-location list that the <b>pPatchLocationListOut</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a> specifies. This list must contain all of the references because the addresses of the allocations might change before the DMA buffer is submitted to the GPU; therefore, the DirectX graphics kernel subsystem will call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_patch">DxgkDdiPatch</a> function to repatch the DMA buffer. </div>
<div> </div>
To unbind an allocation, the display miniport driver can specify an element in the allocation list that references a <b>NULL</b> handle and then can use a patch-location element that references that <b>NULL</b> allocation. Typically, the driver should use the first element of the allocation list (element 0) as the <b>NULL</b> element.

When the display miniport driver translates a command buffer to a DMA buffer, the display miniport driver and user-mode display driver should perform the following actions for the following situations: 

<ul>
<li>
In guaranteed contract DMA mode (for more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/using-the-guaranteed-contract-dma-buffer-model">Using the Guaranteed Contract DMA Buffer Model</a>), the user-mode display driver must guarantee enough resources for the translation command. If enough resources do not exist for the translation, the display miniport driver must reject the DMA buffer.

</li>
<li>
The user-mode display driver should always split up commands that might translate to more than the size of a single DMA buffer because the display miniport driver's <i>DxgkDdiRender</i> function cannot handle a single command that is larger than the size of the DMA buffer and that cannot be split.

</li>
</ul>
<i>DxgkDdiRender</i> should be made pageable.

Support for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a> function is added beginning with Windows 7 for display adapters that support <a href="https://docs.microsoft.com/windows-hardware/drivers/display/gdi-hardware-acceleration">GDI Hardware Acceleration</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_openallocationinfo">DxgkDdiOpenAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_patch">DxgkDdiPatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a>

