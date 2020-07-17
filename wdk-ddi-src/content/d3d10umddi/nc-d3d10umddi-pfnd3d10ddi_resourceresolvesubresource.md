---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCERESOLVESUBRESOURCE
title: PFND3D10DDI_RESOURCERESOLVESUBRESOURCE (d3d10umddi.h)
description: The ResourceResolveSubresource function resolves multiple samples to one pixel.
old-location: display\resourceresolvesubresource.htm
ms.assetid: f9f4a6e2-bc01-477f-a919-ec71871f665b
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_RESOURCERESOLVESUBRESOURCE callback function"]
ms.keywords: PFND3D10DDI_RESOURCERESOLVESUBRESOURCE, PFND3D10DDI_RESOURCERESOLVESUBRESOURCE callback, ResourceResolveSubresource, ResourceResolveSubresource callback function [Display Devices], UserModeDisplayDriverDx10_Functions_bddd44ef-1872-4285-9b04-fdd509e84527.xml, d3d10umddi/ResourceResolveSubresource, display.resourceresolvesubresource
f1_keywords:
 - "d3d10umddi/ResourceResolveSubresource"
 - "ResourceResolveSubresource"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- ResourceResolveSubresource
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_RESOURCERESOLVESUBRESOURCE callback function


## -description


The <i>ResourceResolveSubresource</i> function resolves multiple samples to one pixel.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDstResource* [in]

A handle to the destination resource to resolve to. This resource must have been created as D3D10_USAGE_DEFAULT and single sampled.

### -param Arg3

*DstSubresource* [in]

An index that indicates the destination subresource to resolve to.

### -param Arg4

*hSrcResource* [in]

A handle to the source resource to resolve from.

### -param Arg5

*SrcSubresource* [in]

An index that indicates the source subresource to resolve from.

### -param Arg6

*ResolveFormat* [in]

A DXGI_FORMAT-typed value that indicates how to interpret the contents of the resolved resource.



## -remarks




The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 







The algorithm to resolve multiple samples to one pixel depends on the implementation. 

The resolve operation shares similar restrictions to copy operations that occur in calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopy">ResourceCopy</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion">ResourceCopyRegion</a> functions. That is, both source and destination resources must be the same type (for example, Texture2D), and no stretching or format conversions can occur. The driver can resolve only a whole subresource; therefore, both the source and destination subresources must be equal in dimensions. Because of typeless resources, the following interactions can exist with either the source or destination resource format: 

<ul>
<li>
If each resource is prestructured plus typed, both resources must have the same format type, and that format type must match the format type that was passed in the <i>ResolveFormat</i> parameter (for example, all R32_FLOAT). 

</li>
<li>
If one resource is prestructured plus typeless, the prestructured-plus-typed resource's format must be compatible with the typeless format, and the format type that was passed in the <i>ResolveFormat</i> parameter must match the prestructured-plus-typed format (for example, if the source format is R32_TYPELESS, and the destination format and <i>ResolveFormat</i> are R32_FLOAT). 

</li>
<li>
If both resources are prestructured plus typeless, they must be equal formats, and the format type that was passed in the <i>ResolveFormat</i> parameter can be any format that is compatible with the typeless format. (for example, if the source and destination format are R32_TYPELESS, and <i>ResolveFormat</i> is R32_FLOAT or R32_UINT).

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopy">ResourceCopy</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion">ResourceCopyRegion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

