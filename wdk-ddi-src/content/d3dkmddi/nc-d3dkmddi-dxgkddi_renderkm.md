---
UID: NC:d3dkmddi.DXGKDDI_RENDERKM
title: DXGKDDI_RENDERKM
author: windows-driver-content
description: For display adapters that support GDI hardware acceleration, the DxgkDdiRenderKm function generates a direct memory access (DMA) buffer from the command buffer that the kernel-mode Canonical Display Driver (CDD) passed.
old-location: display\dxgkddirenderkm.htm
old-project: display
ms.assetid: 5841934d-7e0a-4bb8-a7f8-17d8c0af351f
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_RENDERKM, DXGKDDI_RENDERKM callback, DmFunctions_f8138753-f755-410c-b0a0-4422dee9bfb6.xml, DxgkDdiRenderKm, DxgkDdiRenderKm callback function [Display Devices], d3dkmddi/DxgkDdiRenderKm, display.dxgkddirenderkm
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiRenderKm
product: Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_RENDERKM callback function


## -description


For display adapters that support GDI hardware acceleration, the <i>DxgkDdiRenderKm</i> function generates a direct memory access (DMA) buffer from the command buffer that the kernel-mode Canonical Display Driver (CDD) passed.


## -parameters




### -param hContext [in]

[in] A handle to the device context for the DMA and command buffers. The display miniport driver's <a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a> function previously returned this handle in the <b>hContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557567">DXGKARG_CREATECONTEXT</a> structure that the <i>pCreateContext</i> parameter of <i>DxgkDdiCreateContext</i> points to.

If the driver does not support context creation, the Microsoft DirectX graphics kernel subsystem replaces the handle to the context with a handle to the device. The display miniport driver's <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a> function previously returned the device handle in the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557570">DXGKARG_CREATEDEVICE</a> structure that the <i>pCreateDevice</i> parameter of <i>DxgkDdiCreateDevice</i> points to.


### -param pRenderKmArgs [in, out]

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557648">DXGKARG_RENDER</a> structure that contains information about the DMA buffer and a formatted command buffer.

If the display miniport driver supports GDI hardware acceleration, <i>pRenderKmArgs</i>-&gt;<b>pCommand</b> points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562026">DXGK_RENDERKM_COMMAND</a> command buffer.

The driver must translate the input command buffer into DMA buffer commands and build the patch location list.


## -returns



<i>DxgkDdiRenderKm</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The entire command buffer was translated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/5841934d-7e0a-4bb8-a7f8-17d8c0af351f">DxgkDdiRenderKm</a> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
The current DMA buffer is depleted.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/5841934d-7e0a-4bb8-a7f8-17d8c0af351f">DxgkDdiRenderKm</a> detected instruction parameters that graphics hardware could not support; however, the graphics hardware can support the instructions themselves. The driver is not required to return this error code. Instead, it can return STATUS_ILLEGAL_INSTRUCTION when it detects unsupported instruction parameters.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_USER_BUFFER</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/5841934d-7e0a-4bb8-a7f8-17d8c0af351f">DxgkDdiRenderKm</a> detected data or instruction underrun or overrun. That is, the driver received less or more instructions or data than expected. The driver is not required to return this error code. Instead, it can return STATUS_ILLEGAL_INSTRUCTION when it detects data or instruction underrun or overrun.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/5841934d-7e0a-4bb8-a7f8-17d8c0af351f">DxgkDdiRenderKm</a> detected an invalid handle in the command buffer.
       

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver detected an error in the DMA stream. The graphics context device is placed in a lost state if the driver returns this error code. 

</td>
</tr>
</table>
 




## -remarks



The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiRenderKm</i> function to generate a DMA buffer from the command buffer that is passed by the kernel-mode Canonical Display Driver (CDD) provided by the operating system. In addition to the output DMA buffer, the display miniport driver should also generate a list of output patch locations. The video memory manager uses this list to split and patch DMA buffers appropriately.

<div class="alert"><b>Note</b>    Access to the kernel buffers does not require protection from <code>try/except</code> code. </div>
<div> </div>
The display miniport driver is not required to use information that the CDD provides if it can re-create the information more optimally. For example, if the <i>pRender</i>-&gt;<b>pPatchLocationListIn</b> member is empty because the user-mode display driver did not provide an input patch-location list, the display miniport driver can generate the content of the <i>pRender</i>-&gt;<b>pPatchLocationListOut</b> member based on the content of the command buffer instead.

In addition to the device-specific handle, the DirectX graphics kernel subsystem provides the display miniport driver with the last known GPU segment address for each allocation. If allocation index <i>N</i> is currently paged out, the DirectX graphics kernel subsystem sets the <b>SegmentId</b> member of the <i>N</i>th element of the <b>pAllocationList</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff557648">DXGKARG_RENDER</a> to zero. If the <b>SegmentId</b> member of the <i>N</i>th element of the allocation list is not set to zero, the display miniport driver must patch the generated DMA buffer with the provided segment address information before the DirectX graphics kernel subsystem calls the <a href="https://msdn.microsoft.com/363be784-0e3b-4f9a-a643-80857478bbae">DxgkDdiPatch</a> function to repatch the DMA buffer. The driver must perform this initial patching when requested because the DirectX graphics kernel subsystem might not call the <i>DxgkDdiPatch</i> function on a DMA buffer that the driver should have properly patched.

<div class="alert"><b>Note</b>    Even though the driver's <i>DxgkDdiRenderKm</i> function performs the initial DMA buffer patching as described earlier, the driver must still insert all the references to allocations into the output patch-location list that the <b>pPatchLocationListOut</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff557648">DXGKARG_RENDER</a> specifies. This list must contain all of the references because the addresses of the allocations might change before the DMA buffer is submitted to the GPU; therefore, the DirectX graphics kernel subsystem will call the <a href="https://msdn.microsoft.com/363be784-0e3b-4f9a-a643-80857478bbae">DxgkDdiPatch</a> function to repatch the DMA buffer. </div>
<div> </div>
To unbind an allocation, the display miniport driver can specify an element in the allocation list that references a <b>NULL</b> handle and then can use a patch-location element that references that <b>NULL</b> allocation. Typically, the driver should use the first element of the allocation list (element 0) as the <b>NULL</b> element.

In guaranteed contract DMA mode, when the display miniport driver translates a command buffer to a DMA buffer, the CDD must guarantee enough resources for the translation command. If enough resources do not exist for the translation, the display miniport driver must reject the DMA buffer. For more information, see <a href="https://msdn.microsoft.com/fee6f7eb-157b-466d-b482-110a48045283">Using the Guaranteed Contract DMA Buffer Model</a>.

<i>DxgkDdiRenderKm</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544375">D3DDDI_ALLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557567">DXGKARG_CREATECONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557570">DXGKARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560975">DXGK_ALLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562026">DXGK_RENDERKM_COMMAND</a>



<a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a>



<a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>



<a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a>



<a href="https://msdn.microsoft.com/363be784-0e3b-4f9a-a643-80857478bbae">DxgkDdiPatch</a>



<a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a>
 

 

