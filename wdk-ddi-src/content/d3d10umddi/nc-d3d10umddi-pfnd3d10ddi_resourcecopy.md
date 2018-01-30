---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCECOPY
title: PFND3D10DDI_RESOURCECOPY
author: windows-driver-content
description: The ResourceCopy function copies an entire source resource to a destination resource.
old-location: display\resourcecopy.htm
old-project: display
ms.assetid: 9a837f42-0bea-4425-b693-dd7947ac24b1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.resourcecopy, ResourceCopy callback function [Display Devices], ResourceCopy, PFND3D10DDI_RESOURCECOPY, PFND3D10DDI_RESOURCECOPY, d3d10umddi/ResourceCopy, UserModeDisplayDriverDx10_Functions_40047363-38d4-4271-8c24-f9a7ea565079.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	ResourceCopy
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---

# PFND3D10DDI_RESOURCECOPY callback


## -description


The <i>ResourceCopy</i> function copies an entire source resource to a destination resource.


## -prototype


````
PFND3D10DDI_RESOURCECOPY ResourceCopy;

VOID APIENTRY ResourceCopy(
  _In_ D3D10DDI_HDEVICE   hDevice,
  _In_ D3D10DDI_HRESOURCE hDstResource,
  _In_ D3D10DDI_HRESOURCE hSrcResource
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D10DDI_HRESOURCE






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hDstResource [in]

 A handle to the destination resource to copy to.


#### - hSrcResource [in]

 A handle to the source resource to copy from.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section.



## -remarks


The Microsoft Direct3D runtime calls the user-mode display driver's <i>ResourceCopy</i> function to inform the driver to copy from the specified source resource to the specified destination resource. The source and destination resources cannot be the same resource. Both source and destination resources must be the same type of resource and have the same dimensions. The format types (DXGI_FORMAT-typed values) of both resources must be castable to each other. The source and the destination resource must not be currently mapped. In addition, the resource creation flags restrict whether the resource can participate in the copy operation. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>ResourceCopy</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.
<div class="alert"><b>Note</b>  The following sections apply only to Microsoft Direct3D version 10.1 and later (that is, Windows Vista with Service Pack 1 (SP1) and later, and Windows Server 2008 and later).</div><div> </div>The driver can implement a <i>ResourceCopy</i> function that can contain a <b>switch</b> statement to process copying and conversion. That is, the driver can implement one <i>ResourceCopy</i> and can set the <b>pfnResourceConvert</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddi_devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a> structure to point to <i>ResourceCopy</i> along with the <b>pfnResourceCopy</b> member of D3D10_1DDI_DEVICEFUNCS. However, to improve performance, the driver can implement separate <i>ResourceCopy</i> and <i>ResourceConvert</i> functions.

The Direct3D 10.1 version  of <i>ResourceCopy</i> has a major functionality difference from the Direct3D 10.0 version in regard to the <b>ResourceDimension</b> member of <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a> for the source and destination resources that were created in calls to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a> function. For the Direct3D 10.0 version  of <i>ResourceCopy</i>, the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE for the source and destination resources must match. The Direct3D 10.1 version of <i>ResourceCopy</i> allows a slight relaxation for the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE for the source and destination resources. The Direct3D 10.1 version of <i>ResourceCopy</i> allows for the copying of Tex2D source resources on TexCube destination resources or TexCube source resources on Tex2D destination resources. In addition, the distinction between TexCube at the resource level is gone in Direct3D version 10.1. The Direct3D 10.1 version of <i>ResourceCopy</i> only represents whether it can copy a TexCube. In Direct3D version 10.0, copying a resource, validation of a multiple render target, and so on (that is, various operations that required the resource type to be identical) all included the distinction of TexCube to factor into the resource type. In Direct3D version 10.1, the runtime can determine only Tex2D.

The following sections list conditions for copying and converting:

<b>Copying</b>

For copying, <i>ResourceCopy</i> ensures that the source and destination resources were created through the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a> function with the following conditions: 
<ul>
<li>
The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a> structure. 

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
</ul><i>ResourceCopy</i> does not ensure that no subresources are currently mapped. 

<b>Converting</b>

For conversion, <i>ResourceCopy</i> ensures that the source and destination resources were created through the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a> function with the following conditions:
<ul>
<li>
The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a> structure. 

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
</ul><i>ResourceCopy</i> does not ensure that no subresources are currently mapped. 



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddi_devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_RESOURCECOPY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

