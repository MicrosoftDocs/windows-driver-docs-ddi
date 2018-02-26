---
UID: NC:d3dkmddi.DXGKDDI_PRESENT
title: DXGKDDI_PRESENT
author: windows-driver-content
description: The DxgkDdiPresent function copies content from source allocations to a primary surface (and sometimes to off-screen system memory allocations).
old-location: display\dxgkddipresent.htm
old-project: display
ms.assetid: 1a46b129-1e78-44e6-a609-59eab206692b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKDDI_PRESENT, DmFunctions_9dfdaa11-723f-48de-a0d1-5559b5841e7e.xml, DxgkDdiPresent, DxgkDdiPresent callback function [Display Devices], d3dkmddi/DxgkDdiPresent, display.dxgkddipresent
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkDdiPresent
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_PRESENT callback


## -description


The <i>DxgkDdiPresent</i> function copies content from source allocations to a primary surface (and sometimes to off-screen system memory allocations).


## -prototype


````
DXGKDDI_PRESENT DxgkDdiPresent;

NTSTATUS APIENTRY DxgkDdiPresent(
  _In_    const HANDLE          hContext,
  _Inout_       DXGKARG_PRESENT *pPresent
)
{ ... }
````


## -parameters




### -param hContext [in]

[in] A handle to the device context for the copy information. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> function previously returned this handle in the <b>hContext</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createcontext.md">DXGKARG_CREATECONTEXT</a> structure that the <i>pCreateContext</i> parameter of <i>DxgkDdiCreateContext </i>points to. 

If the driver does not support context creation, the Microsoft DirectX graphics kernel subsystem replaces the handle to the context with a handle to the device. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function previously returned the device handle in the <b>hDevice</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a> structure that the <i>pCreateDevice</i> parameter of <i>DxgkDdiCreateDevice </i>points to. 


### -param pPresent [in, out]

[in/out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a> structure that contains information about the copy operation.


## -returns



<i>DxgkDdiPresent</i> returns one of the following values:

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
<i>DxgkDdiPresent</i> successfully copied the content.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY or STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiPresent</i> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
The current direct memory access (DMA) buffer is depleted.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_CANNOTCOLORCONVERT</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver detected a bit-block transfer (bitblt) for color conversion that the device could not perform. The Microsoft Direct3D runtime prevents the application from continuing, and the application receives a failure to copy content.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGED_INSTRUCTION</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiPresent</i> detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current central processing unit [CPU] process).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ILLEGAL_INSTRUCTION</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiPresent</i> detected instructions that graphics hardware cannot support.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiPresent</i> detected an invalid handle in the command buffer.

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



The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiPresent</i> function to copy content from source allocations typically to the primary surface. (This function can also copy content to an off-screen system memory allocation.) Because a primary surface is loosely defined, <i>DxgkDdiPresent</i> can be implemented for the following scenarios: 

<ul>
<li>
Depending on the position of the window, the <i>DxgkDdiPresent</i> function must be performed across different primaries that can be on the same adapter or across different adapters.

</li>
<li>
The primary is on a remote monitor and is accessed through a terminal services client or Microsoft NetMeeting.

</li>
<li>
A mode switch recently occurred and the primary format is different from the source format, so a color conversion is needed. In addition, the <i>DxgkDdiPresent</i> operation can be clipped because of window clipping and ordering.

</li>
</ul>
Because the preceding scenarios can change asynchronously, the user-mode display driver cannot compile hardware instructions for the display miniport driver's <i>DxgkDdiPresent</i> function in advance. The display miniport driver must create hardware commands for the actual <i>DxgkDdiPresent</i> operation, and they must be placed in an output DMA buffer. After the display miniport driver's <i>DxgkDdiPresent</i> function is called to generate the DMA buffer, the operating system guarantees that a scenario change will not occur before that buffer is rendered. 

The display miniport driver is not required to be aware of the specifics of the preceding scenarios as long as the driver supports the following abstractions: 

<ul>
<li>In a copy operation from a video memory source to a primary video or system memory destination, a copy from an off-screen system memory source to the primary destination, a copy from and to the primary, or a copy from the primary source to an off-screen system memory destination, the source is specified by the <b>hDeviceSpecificAllocation</b> member of the <b>pAllocationList</b>[DXGK_PRESENT_SOURCE_INDEX] array element of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a> structure that the <i>pPresent</i> parameter of <i>DxgkDdiPresent</i> points to. The destination, which is either the current primary of the device or an off-screen system memory allocation, is specified by the <b>hDeviceSpecificAllocation</b> member of the <b>pAllocationList</b>[DXGK_PRESENT_DESTINATION_INDEX] array element of DXGKARG_PRESENT. If the destination equals the source (that is, destination == source), the copy operation is a screen-to-screen bit-block transfer (bitblt). Therefore, the graphics subsystem sets the source and destination to the following values: <ul>
<li>destination != <b>NULL</b> (that is, destination == nonNULL)</li>
<li>source != <b>NULL</b> (that is, source == nonNULL) </li>
</ul>
</li>
<li>In a video memory flip from the current allocation to another allocation, the source can be specified  by the operating system and set in the <b>hDeviceSpecificAllocation</b> member of the <b>pAllocationList</b>[DXGK_PRESENT_SOURCE_INDEX] array element of DXGKARG_PRESENT. The graphics subsystem sets the source and destination to  the following  values: <ul>
<li>destination == <b>NULL</b></li>
<li>source != <b>NULL</b> (that is, source == nonNULL) </li>
</ul>
<div class="alert"><b>Note</b>    A no-op flip can be performed from the same source allocation as the currently scanned-out allocation. A no-op flip is used to insert a queued wait for a vertical blank in the rendering stream. The display miniport driver should insert a hardware flip command as if it were flipping to another allocation.</div>
<div> </div>
</li>
<li>In a color-fill operation to the primary surface, no source allocation is required and the destination is a primary allocation handle that is specified by the <b>hDeviceSpecificAllocation</b> member of the <b>pAllocationList</b>[DXGK_PRESENT_DESTINATION_INDEX] array element of DXGKARG_PRESENT. The <b>Color</b> member of DXGKARG_PRESENT is typically in the D3DDDIFMT_A8R8G8B8 format from the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> enumeration type. However, when the primary format is palettized RGB, <b>Color</b> contains the palette index. Therefore, the graphics subsystem sets the source and destination to the following values: <ul>
<li>destination != <b>NULL</b> (that is, destination == nonNULL)</li>
<li>source == <b>NULL</b></li>
</ul>
</li>
</ul>
For all of the <i>DxgkDdiPresent</i> scenarios to operate correctly, the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function should set the <b>DmaBufferSize</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_deviceinfo.md">DXGK_DEVICEINFO</a> structure to be large enough to hold the hardware commands that are needed to present at least one <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> rectangle to the display or off-screen target. However, the driver's <i>DxgkDdiPresent</i> function can return STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER if the number of subrectangles in the <i>DxgkDdiPresent</i> scenario depletes the current DMA buffer and the driver requires another DMA buffer to continue. 

The graphics subsystem then acquires a new DMA buffer and calls the driver's <i>DxgkDdiPresent</i> function again with the same list of RECT structures as the previous <i>DxgkDdiPresent</i> call. The driver must use the <b>MultipassOffset</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a> structure that is pointed to by <i>pPresent </i>to record the amount of progress made in completing the RECT list in the previous call to <i>DxgkDdiPresent</i> so that the driver can continue from where it stopped with the new DMA buffer. When the driver's <i>DxgkDdiPresent</i> function completes the list of RECT structures, it returns STATUS_SUCCESS.

In addition to generating a DMA buffer, the display miniport driver must generate a patch-location list that indicates the various offsets within the DMA buffer that must be patched later when physical addresses for allocations are known. At times, the video memory manager provides the driver with pre-patched information (that is, the last know physical addresses for the source and destination) in the allocation list. 

When the video memory manager provides this information, the driver must generate the DMA buffer by determining that these physical addresses are the final addresses that the DirectX graphics kernel subsystem will provide. The graphics subsystem might not call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function on the DMA buffer to patch it again later. Therefore, the driver must use the pre-patch information to generate the DMA buffer properly. Pre-patched information is provided for element <i>N</i> when the <b>SegmentId</b> member of the <i>N</i>th element of the <b>pAllocationList</b> array of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a> is nonzero.

<div class="alert"><b>Note</b>    Even though the driver's <i>DxgkDdiPresent</i> function pre-patches the DMA buffer, the driver must still insert all of the references to allocations into the output patch-location list that the <b>pPatchLocationListOut</b> member of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a> specifies. The driver must insert these references  because the addresses of the allocations might change before the DMA buffer is submitted to the GPU; therefore, the DirectX graphics kernel subsystem will call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function to repatch the DMA buffer. </div>
<div> </div>
If the driver supports rotation (that is, reports support for rotated modes in the <b>RotationSupport</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation.md">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> structure in a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a> function), the driver must be able to perform rotated bit-block transfers (bitblt) from source to destination. When the <b>Rotate</b> bit-field flag is specified in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentflags.md">DXGK_PRESENTFLAGS</a> structure for the <b>Flags</b> member of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a>, the driver should apply the rotation as if going from a non-rotated surface to the final orientation of the current source. 

The primary allocation of a source is specified in the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a> function. If multiple paths originate from the given source (clone mode), the display miniport driver must ensure that the outputs are correctly rotated given the path rotation mode for the different targets. All of the parameters that are supplied to <i>DxgkDdiPresent</i> are rotation agnostic. The source and target rectangles could both be the entire screen as clients perceive it (for example, 768 x 1024). 

<div class="alert"><b>Note</b>    This situation does not address full-screen Direct3D applications in rotated mode. </div>
<div> </div>
If the display miniport driver previously indicated, in a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function, that it supports a memory mapped I/O (MMIO)-based flip (by setting the <b>FlipOnVSyncMmIo</b> bit-field flag in the <b>FlipCaps</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure to <b>TRUE</b>), the driver's <i>DxgkDdiPresent</i> function is subsequently called with the <b>pDmaBuffer</b> member of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a> set to <b>NULL</b> because a MMIO-based flip does not require a DMA buffer to run on the GPU. Instead, the driver's <i>DxgkDdiPresent</i> function must validate the source surface and program flip hardware as required. The DirectX graphics kernel subsystem calls the driver's <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> function to run this type of flip.

<i>DxgkDdiPresent</i> should be made pageable.




## -see-also

<b>DXGKARG_PRESENT</b>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentflags.md">DXGK_PRESENTFLAGS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_deviceinfo.md">DXGK_DEVICEINFO</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createcontext.md">DXGKARG_CREATECONTEXT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_PRESENT callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

