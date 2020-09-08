---
UID: NS:dxgiddi.DXGI_DDI_BASE_FUNCTIONS
title: DXGI_DDI_BASE_FUNCTIONS (dxgiddi.h)
description: The DXGI_DDI_BASE_FUNCTIONS structure contains functions that the user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, and managing a full-screen transition.
old-location: display\dxgi_ddi_base_functions.htm
tech.root: display
ms.assetid: c9fd9b21-4338-4633-903f-308763cbc301
ms.date: 05/10/2018
keywords: ["DXGI_DDI_BASE_FUNCTIONS structure"]
ms.keywords: DXGI_DDI_BASE_FUNCTIONS, DXGI_DDI_BASE_FUNCTIONS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_f33992c1-f203-4058-a6c4-844b2ff8ffa9.xml, display.dxgi_ddi_base_functions, dxgiddi/DXGI_DDI_BASE_FUNCTIONS
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
req.typenames: DXGI_DDI_BASE_FUNCTIONS
f1_keywords:
 - DXGI_DDI_BASE_FUNCTIONS
 - dxgiddi/DXGI_DDI_BASE_FUNCTIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxgiddi.h
api_name:
 - DXGI_DDI_BASE_FUNCTIONS
---

# DXGI_DDI_BASE_FUNCTIONS structure


## -description

The DXGI_DDI_BASE_FUNCTIONS structure contains functions that the user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, and managing a full-screen transition.

## -struct-fields

### -field pfnPresent

Pointer to the PresentDXGI function that notifies the user-mode display driver that an application finished rendering and requests that the driver display to the destination surface. 

The <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_present">DXGI_DDI_ARG_PRESENT</a> structure that the <i>pPresentData</i> parameter points to is the same handle that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function passed back to the runtime in the <b>hDrvDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure. Therefore, driver writers must define the type of this handle carefully. In addition, drivers can supply different implementations of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a> function based on which DDI implementation handled the call to <b>CreateDevice(D3D10)</b>. The runtime will never mix driver handles across DDI implementations. Similarly, the <b>hSurfaceToPresent</b> and <b>hDstResource</b> members of <b>DXGI_DDI_ARG_PRESENT</b> are also driver-defined resource handles that the driver returned to the runtime in previous calls to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function.

The <b>pDXGIContext</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_present">DXGI_DDI_ARG_PRESENT</a> is an opaque communication mechanism. The runtime passes this DXGI context to the driver. The driver should copy this DXGI context unchanged to the <b>pDXGIContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgiddicb_present">DXGIDDICB_PRESENT</a> structure when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_presentcb">pfnPresentCbDXGI</a> function. 

The driver must submit all partially built render data (command buffers) using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a> function. Thereafter, the driver must translate the resource handle parameters into kernel handles and use those kernel handles in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_presentcb">pfnPresentCbDXGI</a>.

<div class="alert"><b>Note</b>    When the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a> function copies sRGB-formatted content from a source surface to a non-sRGB destination surface, the driver should copy the sRGB content unchanged (that is, the driver should not perform the sRGB to linear conversion).</div>
<div> </div>


#### pPresentData

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_present">DXGI_DDI_ARG_PRESENT</a> structure that describes how to display to the destination surface.

### -field pfnGetGammaCaps

The <i>GetGammaCapsDXGI</i> function retrieves gamma capabilities.



#### pGammaData

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_get_gamma_control_caps">DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS</a> structure that contains gamma capabilities.

### -field pfnSetDisplayMode

A pointer to the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">SetDisplayModeDXGI</a> function.

### -field pfnSetResourcePriority

The <i>SetResourcePriorityDXGI</i> function sets the eviction-from-memory priority for a resource.

The Microsoft Direct3D runtime calls <i>SetResourcePriorityDXGI</i> to set the priority level for a resource. The user-mode display driver should translate the resource handle that is supplied in the <b>hResource</b> member of the DXGI_DDI_ARG_SETRESOURCEPRIORITY structure that is pointed to by <i>pPriorityData</i> to an allocation handle. After the driver makes this translation, the driver should pass the resulting handle in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setprioritycb">pfnSetPriorityCb</a> function.



#### pPriorityData

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_setresourcepriority">DXGI_DDI_ARG_SETRESOURCEPRIORITY</a> structure that describes the priority level to set a resource to.

### -field pfnQueryResourceResidency

This function determines the residency of the given list of resources.

The Microsoft Direct3D runtime calls the user-mode display driver's <i>QueryResourceResidencyDXGI</i> function for applications to determine if the operating system will incur a significant stall at draw time if the system must make resources GPU-accessible. The information that is returned from <i>QueryResourceResidencyDXGI</i> is an approximation of the residency of resources because the resources might become demoted before applications use the resources.

<i>QueryResourceResidencyDXGI</i> must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryresidencycb">pfnQueryResidencyCb</a> function. <b>pfnQueryResidencyCb</b> returns the residency status of a resource in the elements of the array that is specified by the <b>pResidencyStatus</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_queryresidency">D3DDDICB_QUERYRESIDENCY</a> structure. If <b>pfnQueryResidencyCb</b> returns D3DDDI_RESIDENCYSTATUS_NOTRESIDENT for any query, <i>QueryResourceResidencyDXGI</i> must return S_NOT_RESIDENT. If <b>pfnQueryResidencyCb</b> returns D3DDDI_RESIDENCYSTATUS_RESIDENTINSHAREDMEMORY for any query and does not return D3DDDI_RESIDENCYSTATUS_NOTRESIDENT for any query, <i>QueryResourceResidencyDXGI</i> must return S_RESIDENT_IN_SHARED_MEMORY. <i>QueryResourceResidencyDXGI</i> must return S_OK only if all calls to <b>pfnQueryResidencyCb</b> for all queries return D3DDDI_RESIDENCYSTATUS_RESIDENTINGPUMEMORY.

For each resource that the runtime queries through a call to <i>QueryResourceResidencyDXGI</i>, the user-mode display driver must determine which allocations that belong to the resource to query through a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryresidencycb">pfnQueryResidencyCb</a>. For a resource that owns a single allocation, the determination is simple--the driver will query that allocation. However, if a resource owns multiple allocations, the determination is more difficult. The driver must determine which allocations that an application will likely use for rendering, and the driver must query only those allocations. For example, if a resource owns an allocation that is used for rendering and a scratch allocation that handles a lock operation, the driver should query only for the residency of the first allocation, because an application will most likely not use the second allocation for rendering.

<div class="alert"><b>Note</b>    Because the runtime does not support residency-querying of system memory resources, the runtime will always fail requests from applications for the residency status of system memory resources and will never call the user-mode display driver's <i>QueryResourceResidencyDXGI</i> function for these system memory resources.</div>
<div> </div>


#### pResidencyData

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_queryresourceresidency">DXGI_DDI_ARG_QUERYRESOURCERESIDENCY</a> structure that describes a list of resources that residency is verified on.

### -field pfnRotateResourceIdentities

Rotates a list of resources.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">RotateResourceIdentitiesDXGI</a> function must exchange identities of the array of resources that are passed in the <b>pResources</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_rotate_resource_identities">DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES</a> structure that the <i>pRotateData</i> parameter points to. For example, if the array of resources refers to resources X, Y, and Z, in increasing array index order, <i>RotateResourceIdentitiesDXGI</i> must rotate those handles to refer to Y, Z, and X, in increasing array index order. In particular, the user-mode display driver should swap the kernel handles of the corresponding resources. However, the driver should not swap the corresponding runtime (RT) handles. The runtime calls <i>RotateResourceIdentitiesDXGI</i> to rotate back buffers during presentation. Therefore, a call to <i>RotateResourceIdentitiesDXGI</i> is infrequent. The runtime can specify the D3D10_DDI_BIND_PRESENT flag in the <b>BindFlags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> structure when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function to indicate that the resource can participate in a rotate operation. 

The user-mode display driver must also handle other aspects of exchanging identities. For example, in Direct3D version 10, views can refer to resources; and such views can have resource addresses embedded in them. Therefore, the driver must re-create such views. Also, the driver might be required to reapply currently bound views.

Beginning in Windows 8, the driver must support rotation of stereo back buffers.



#### pRotateData

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_rotate_resource_identities">DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES</a> structure that describes a list of resources to rotate.

### -field pfnBlt

Copies the contents of a source surface to a destination surface and may rotate the contents.

The Direct3D runtime might set the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a> structure that the <i>pBltData</i> parameter points to in such a way as to require the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> function to perform a <a href="https://docs.microsoft.com/windows-hardware/drivers/">bit-block transfer (bitblt)</a> operation that resolves multi-sampled resources, performs color-format conversion, and performs a stretch or shrink all at once. However, the Direct3D runtime will never set the <b>Flags</b> member of <b>DXGI_DDI_ARG_BLT</b> to zero (that is, no flags set) together with the <b>DXGI_DDI_MODE_ROTATION_IDENTITY</b> value set in the <b>Rotate</b> member of <b>DXGI_DDI_ARG_BLT</b> (that is, to indicate no rotation) to perform a straight memory copy operation. Instead, unless both resources are multi-sampled, the Direct3D runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopy">ResourceCopy</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion">ResourceCopyRegion</a> function to perform a straight memory copy operation.

The quality of the stretch or shrink that the user-mode display driver performs must be as good as the stretch or shrink that a bilinear filter performs. 

The Direct3D runtime will call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> function infrequently. That is, the runtime should call <i>BltDXGI</i> no more than once or twice per frame because the runtime uses <i>BltDXGI</i> primarily to support a presentation.

 When the runtime calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> for a presentation, the runtime sets the <b>Present</b> bit-field flag in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a>. The runtime sets the <b>Present</b> bit-field flag to inform the driver that there are extra requirements for the bitblt and that extra synchronization may be necessary (for example, the runtime might need to perform extra synchronization in computer configurations that contain two graphics adapters that each handle separate parts of the display). When the <b>Present</b> bit-field flag is set, the driver should perform a copy operation from an application's back buffers to the shared surface of the DWM. Because synchronization for this type of copy operation is inexact, tearing artifacts should be the worst type of artifacts that a user experiences. For this type of copy operation, the driver should not use a multi-pass approach by first resolving into the destination surface and then color converting the results in-place because the possible artifacts would be much worse.

If the driver supports returning <b>DXGI_DDI_ERR_UNSUPPORTED</b> during the creation of a primary surface (that is, returning <b>DXGI_DDI_ERR_UNSUPPORTED</b> from a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function with the <b>D3D10_DDI_BIND_PRESENT</b> flag set in the <b>BindFlags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> along with the <b>pPrimaryDesc</b> member of <b>D3D10DDIARG_CREATERESOURCE</b> set to non-<b>NULL</b>), the driver must also support rotation during a copy operation. If the driver never returns <b>DXGI_DDI_ERR_UNSUPPORTED</b> from a call to its <i>CreateResource(D3D10)</i> function, the runtime will never pass the <b>DXGI_DDI_MODE_ROTATION_ROTATE90</b>, <b>DXGI_DDI_MODE_ROTATION_ROTATE180</b>, or <b>DXGI_DDI_MODE_ROTATION_ROTATE270</b> value to the <b>Rotate</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a>. Therefore, in this situation, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> function is not required to support rotation.

The runtime sets a value in the <b>Rotate</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a> to indicate the number of degrees to rotate counter-clockwise the contents of the source before the driver copies the contents to the destination. Rotation is specified in increments of 90 degrees.

<div class="alert"><b>Note</b>    When the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> function copies sRGB-formatted content from a source surface to a non-sRGB destination surface, the driver should copy the sRGB content unchanged (that is, the driver should not perform the sRGB to linear conversion).</div>
<div> </div>
<b>Source restrictions</b>

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> function always uses a whole source subresource (versus some sub-rectangular area) to perform the bitblt operation. In addition, the source is a <b>D3D10DDIRESOURCE_TEXTURE2D</b> representation (specified in the <b>ResourceDimension</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> when the source is created in a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function). When the runtime sets the <b>Resolve</b> bitfield in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a>, the source is a multi-sampled resource. The source resource is restricted to a resource in which the <b>D3D10_DDI_BIND_PRESENT</b> flag was set in the <b>BindFlags</b> member of <b>D3D10DDIARG_CREATERESOURCE</b>. The format of the source (specified in the <b>Format</b> member of <b>D3D10DDIARG_CREATERESOURCE</b>) is restricted to display mode formats, specified by the following values from the <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> enumeration: 

<ul>
<li>
<b>DXGI_FORMAT_B5G6R5_UNORM</b>

</li>
<li>
<b>DXGI_FORMAT_B5G5R5A1_UNORM</b>

</li>
<li>
<b>DXGI_FORMAT_B8G8R8A8_UNORM</b> (See Note below.)

</li>
<li>
<b>DXGI_FORMAT_B8G8R8X8_UNORM</b>

</li>
<li>
<b>DXGI_FORMAT_R16G16B16A16_FLOAT</b>

</li>
<li>
<b>DXGI_FORMAT_R10G10B10A2_UNORM</b>

</li>
<li>
<b>DXGI_FORMAT_R8G8B8A8_UNORM</b>

</li>
<li>
<b>DXGI_FORMAT_R8G8B8A8_UNORM_SRGB</b>

</li>
</ul>
<div class="alert"><b>Note</b>  If the driver supports the source format <b>DXGI_FORMAT_B8G8R8A8_UNORM</b>, these restrictions apply:<ul>
<li>When the driver performs a bitblt operation from a floating-point format to an integer format such as BGRA8888, it must implicitly encode gamma into the results.</li>
<li>Conversely, when the driver performs a bitblt operation from an integer format to a floating-point format, it must implicitly remove gamma encoding from the results.</li>
</ul>
</div>
<div> </div>
<b>Destination restrictions</b>

The destination is also a <b>D3D10DDIRESOURCE_TEXTURE2D</b> representation. The format of the destination is also restricted to display mode formats. The destination resource is restricted to a resource that is bound as a render target (<b>D3D10_DDI_BIND_RENDER_TARGET</b> set in the <b>BindFlags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a>).

<b>Creating a stereo back buffer</b>

Beginning in Windows 8, if the driver must create a stereo back buffer, it should set members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> structure, respectively, pointed to by the <i>pCreateResource</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a> functions, as follows:

<ol>
<li>Set the <b>ArraySize</b> member to a value of 2.</li>
<li>Set the <b>D3D10_DDI_BIND_PRESENT</b> flag value in the <b>BindFlags</b> member.</li>
</ol>
Additionally, to support stereo presentation, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> function must allow any values for the <b>DstSubresource</b> and <b>SrcSubresource</b> members of  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a> structure that are within the range of the source and destination resources.



#### pBltData

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a> structure that describes the parameters of a bit-block transfer (bitblt).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_args">DXGI_DDI_BASE_ARGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">GetGammaCapsDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">QueryResourceResidencyDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">RotateResourceIdentitiesDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">SetDisplayModeDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">SetResourcePriorityDXGI</a>

