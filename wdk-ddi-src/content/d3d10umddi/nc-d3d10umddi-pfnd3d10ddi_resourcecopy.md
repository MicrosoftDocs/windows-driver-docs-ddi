---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCECOPY
title: PFND3D10DDI_RESOURCECOPY (d3d10umddi.h)
description: The ResourceCopy function copies an entire source resource to a destination resource.
old-location: display\resourcecopy.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_RESOURCECOPY callback function"]
ms.keywords: PFND3D10DDI_RESOURCECOPY, PFND3D10DDI_RESOURCECOPY callback, ResourceCopy, ResourceCopy callback function [Display Devices], UserModeDisplayDriverDx10_Functions_40047363-38d4-4271-8c24-f9a7ea565079.xml, d3d10umddi/ResourceCopy, display.resourcecopy
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_RESOURCECOPY
 - d3d10umddi/PFND3D10DDI_RESOURCECOPY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_RESOURCECOPY
---

# PFND3D10DDI_RESOURCECOPY callback function


## -description

The <i>ResourceCopy</i> function copies an entire source resource to a destination resource.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDstResource* [in]

A handle to the destination resource to copy to.

### -param Arg3

*hSrcResource* [in]

A handle to the source resource to copy from.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 







The Microsoft Direct3D runtime calls the user-mode display driver's <i>ResourceCopy</i> function to inform the driver to copy from the specified source resource to the specified destination resource. The source and destination resources cannot be the same resource. Both source and destination resources must be the same type of resource and have the same dimensions. The format types (DXGI_FORMAT-typed values) of both resources must be castable to each other. The source and the destination resource must not be currently mapped. In addition, the resource creation flags restrict whether the resource can participate in the copy operation. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>ResourceCopy</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

<div class="alert"><b>Note</b>  The following sections apply only to Microsoft Direct3D version 10.1 and later (that is, Windows Vista with Service Pack 1 (SP1) and later, and Windows Server 2008 and later).</div>
<div> </div>
The driver can implement a <i>ResourceCopy</i> function that can contain a <b>switch</b> statement to process copying and conversion. That is, the driver can implement one <i>ResourceCopy</i> and can set the <b>pfnResourceConvert</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddi_devicefuncs">D3D10_1DDI_DEVICEFUNCS</a> structure to point to <i>ResourceCopy</i> along with the <b>pfnResourceCopy</b> member of D3D10_1DDI_DEVICEFUNCS. However, to improve performance, the driver can implement separate <i>ResourceCopy</i> and <i>ResourceConvert</i> functions.

The Direct3D 10.1 version  of <i>ResourceCopy</i> has a major functionality difference from the Direct3D 10.0 version in regard to the <b>ResourceDimension</b> member of <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> for the source and destination resources that were created in calls to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function. For the Direct3D 10.0 version  of <i>ResourceCopy</i>, the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE for the source and destination resources must match. The Direct3D 10.1 version of <i>ResourceCopy</i> allows a slight relaxation for the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE for the source and destination resources. The Direct3D 10.1 version of <i>ResourceCopy</i> allows for the copying of Tex2D source resources on TexCube destination resources or TexCube source resources on Tex2D destination resources. In addition, the distinction between TexCube at the resource level is gone in Direct3D version 10.1. The Direct3D 10.1 version of <i>ResourceCopy</i> only represents whether it can copy a TexCube. In Direct3D version 10.0, copying a resource, validation of a multiple render target, and so on (that is, various operations that required the resource type to be identical) all included the distinction of TexCube to factor into the resource type. In Direct3D version 10.1, the runtime can determine only Tex2D.

The following sections list conditions for copying and converting:

<b>Copying</b>

For copying, <i>ResourceCopy</i> ensures that the source and destination resources were created through the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function with the following conditions: 

<ul>
<li>
The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> structure. 

</li>
<li>
The source and destination resources were created with the same resource type and dimensionality (buffer, one-dimensional (1-D) texture, and so on) by setting the same value in the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE.

</li>
<li>
The source and destination resources are not part of the exact same resource. 

</li>
<li>
Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE is in the same typeless group. 

</li>
<li>
The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. 

</li>
</ul>
<i>ResourceCopy</i> does not ensure that no subresources are currently mapped. 

<b>Converting</b>

For conversion, <i>ResourceCopy</i> ensures that the source and destination resources were created through the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function with the following conditions:

<ul>
<li>
The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> structure. 

</li>
<li>
The source and destination resources were created with the same resource type (buffer, one-dimensional (1-D) texture, and so on) by setting the same value in the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE.

</li>
<li>
The dimensions of the source and destination resources match up for conversion. 

</li>
<li>
The source and destination resources are not part of the exact same resource. 

</li>
<li>
Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE supports the appropriate conversion operation. For mipped-block compressed resources, the dimensions are all validated to be a power of two. 

</li>
<li>
The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. 

</li>
</ul>
<i>ResourceCopy</i> does not ensure that no subresources are currently mapped.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddi_devicefuncs">D3D10_1DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

