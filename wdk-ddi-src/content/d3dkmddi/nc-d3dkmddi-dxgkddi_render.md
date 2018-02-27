---
UID: NC:d3dkmddi.DXGKDDI_RENDER
title: DXGKDDI_RENDER
author: windows-driver-content
description: The DxgkDdiRender function generates a direct memory access (DMA) buffer from the command buffer that the user-mode display driver passed.
old-location: display\dxgkddirender.htm
old-project: display
ms.assetid: fd634768-5e1e-4f40-82fd-5ef69148c3d7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKDDI_RENDER, DmFunctions_e6f475cd-e097-4ea7-9f66-9e0b2d78d46b.xml, DxgkDdiRender, DxgkDdiRender callback function [Display Devices], d3dkmddi/DxgkDdiRender, display.dxgkddirender
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiRender
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_RENDER callback


## -description


The <i>DxgkDdiRender</i> function generates a direct memory access (DMA) buffer from the command buffer that the user-mode display driver passed.


## -prototype


````
DXGKDDI_RENDER DxgkDdiRender;

NTSTATUS APIENTRY DxgkDdiRender(
  _In_    const HANDLE         hContext,
  _Inout_       DXGKARG_RENDER *pRender
)
{ ... }
````


## -parameters




### -param hContext [in]

[in] A handle to the device context for the DMA and command buffers. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> function previously returned this handle in the <b>hContext</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createcontext.md">DXGKARG_CREATECONTEXT</a> structure that the <i>pCreateContext</i> parameter of <i>DxgkDdiCreateContext </i>points to. 

If the driver does not support context creation, the Microsoft DirectX graphics kernel subsystem replaces the handle to the context with a handle to the device. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function previously returned the device handle in the <b>hDevice</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a> structure that the <i>pCreateDevice</i> parameter of <i>DxgkDdiCreateDevice </i>points to. 


### -param pRender [in, out]

[in/out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_render.md">DXGKARG_RENDER</a> structure that contains information about the DMA and command buffers.


## -returns



<i>DxgkDdiRender</i> returns one of the following values:

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
<i>DxgkDdiRender</i> could not allocate memory that was required for it to complete.

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
<dt><b>STATUS_PRIVILEGED_INSTRUCTION</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiRender</i> detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current central processing unit [CPU] process).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ILLEGAL_INSTRUCTION</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiRender</i> detected instructions that graphics hardware could not support.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiRender</i> detected instruction parameters that graphics hardware could not support; however, the graphics hardware can support the instructions themselves. The driver is not required to return this error code. Instead, it can return STATUS_ILLEGAL_INSTRUCTION when it detects unsupported instruction parameters.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_USER_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiRender</i> detected data or instruction underrun or overrun. That is, the driver received less or more instructions or data than expected. The driver is not required to return this error code. Instead, it can return STATUS_ILLEGAL_INSTRUCTION when it detects data or instruction underrun or overrun.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiRender</i> detected an invalid handle in the command buffer.
       

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiRender</i> (that is, submitted the command buffer). 

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



The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiRender</i> function to generate a DMA buffer from the command buffer that the user-mode display driver passed. When the display miniport driver translates from the command buffer to the DMA buffer, the driver should also validate the command buffer to ensure that the command buffer does not contain any privileged commands or commands that can be used to access memory that does not belong to the process. In addition to the output DMA buffer, the display miniport driver should also generate a list of output patch locations. The video memory manager uses this list to split and patch DMA buffers appropriately. 

Both the command buffer <b>pCommand</b> and the input patch-location list <b>pPatchLocationListIn</b> that the user-mode display driver generates are allocated from the user-mode address space and are passed to the display miniport driver untouched. The display miniport driver must use <code>__try/__except</code> code on any access to the buffer and list and must validate the content of the buffer and list before copying the content to the respective kernel buffers (that is, before copying the content of the <b>pCommand</b> member to the <b>pDmaBuffer</b> member and the content of the <b>pPatchLocationListIn</b> member to the <b>pPatchLocationListOut</b> member, which are all members of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_render.md">DXGKARG_RENDER</a> structure that the <i>pRender</i> parameter points to).

Here's an example of how display miniport drivers should access these buffers using  <code>__try</code> and <code>__except</code> logic. <b>AllocationListIn</b> points to the user-mode buffer.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>__try
  {
    for (Index = 0; Index &lt; AllocationListInSize; AllocationTable++, 
           AllocationListIn++, AllocationListOut++, Index++) 
    {
      D3DKMT_HANDLE AllocationHandle = AllocationListIn-&gt;hAllocation;
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
</pre>
</td>
</tr>
</table></span></div>
<div class="alert"><b>Note</b>    Access to the kernel buffers does not require protection from <code>try/except</code> code.</div>
<div> </div>
The display miniport driver is not required to use information that the user-mode display driver provides if recreating the information is more optimal. For example, if <b>pPatchLocationListIn</b> is empty because the user-mode display driver did not provide an input patch-location list, the display miniport driver can generate the content of <b>pPatchLocationListOut</b> based on the content of the command buffer instead.

The allocation list that the user-mode display driver provides is validated, copied, and converted into a kernel-mode allocation list during the kernel transition. The DirectX graphics kernel subsystem converts each <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationlist.md">D3DDDI_ALLOCATIONLIST</a> element into a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationlist.md">DXGK_ALLOCATIONLIST</a> element by converting the D3DKMT_HANDLE-typed handle that the user-mode display driver provides into a device-specific handle, which the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a> function returns. The index of each allocation and the write status of the allocation (that is, the setting of the <b>WriteOperation</b> bit-field flag) remains constant during the conversion. 

In addition to the device-specific handle, the DirectX graphics kernel subsystem provides the display miniport driver with the last known GPU segment address for each allocation. If allocation index <i>N</i> is currently paged out, the DirectX graphics kernel subsystem sets the <b>SegmentId</b> member of the <i>N</i>th element of the <b>pAllocationList</b> member of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_render.md">DXGKARG_RENDER</a> to zero. If the <b>SegmentId</b> member of the <i>N</i>th element of the allocation list is not set to zero, the display miniport driver must pre-patch the generated DMA buffer with the provided segment address information. The driver must pre-patch when requested because the DirectX graphics kernel subsystem might not call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function on a DMA buffer that the driver should have properly pre-patched. 

<div class="alert"><b>Note</b>    Even though the driver's <i>DxgkDdiRender</i> function pre-patches the DMA buffer, the driver must still insert all of the references to allocations into the output patch-location list that the <b>pPatchLocationListOut</b> member of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_render.md">DXGKARG_RENDER</a> specifies. This list must contain all of the references because the addresses of the allocations might change before the DMA buffer is submitted to the GPU; therefore, the DirectX graphics kernel subsystem will call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function to repatch the DMA buffer. </div>
<div> </div>
To unbind an allocation, the display miniport driver can specify an element in the allocation list that references a <b>NULL</b> handle and then can use a patch-location element that references that <b>NULL</b> allocation. Typically, the driver should use the first element of the allocation list (element 0) as the <b>NULL</b> element.

When the display miniport driver translates a command buffer to a DMA buffer, the display miniport driver and user-mode display driver should perform the following actions for the following situations: 

<ul>
<li>
In guaranteed contract DMA mode (for more information, see <a href="https://msdn.microsoft.com/fee6f7eb-157b-466d-b482-110a48045283">Using the Guaranteed Contract DMA Buffer Model</a>), the user-mode display driver must guarantee enough resources for the translation command. If enough resources do not exist for the translation, the display miniport driver must reject the DMA buffer.

</li>
<li>
The user-mode display driver should always split up commands that might translate to more than the size of a single DMA buffer because the display miniport driver's <i>DxgkDdiRender</i> function cannot handle a single command that is larger than the size of the DMA buffer and that cannot be split.

</li>
</ul>
<i>DxgkDdiRender</i> should be made pageable.


    Support for the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_renderkm.md">DxgkDdiRenderKm</a> function is added beginning with Windows 7 for display adapters that support <a href="https://msdn.microsoft.com/03db58e6-a6d5-4b6f-ba71-d22a985f9c57">GDI Hardware Acceleration</a>.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_render.md">DXGKARG_RENDER</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createcontext.md">DXGKARG_CREATECONTEXT</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_renderkm.md">DxgkDdiRenderKm</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationlist.md">D3DDDI_ALLOCATIONLIST</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationlist.md">DXGK_ALLOCATIONLIST</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_RENDER callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

