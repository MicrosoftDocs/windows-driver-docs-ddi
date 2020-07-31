---
UID: NC:d3dumddi.PFND3DDDI_RESOLVESHAREDRESOURCE
title: PFND3DDDI_RESOLVESHAREDRESOURCE (d3dumddi.h)
description: The ResolveSharedResource function informs a user-mode display driver that ownership of a shared surface changed or that a surface is being used for GDI interoperation.
old-location: display\resolvesharedresource.htm
tech.root: display
ms.assetid: 8ad9130e-bade-4fd2-b345-b6361fd001ef
ms.date: 05/10/2018
keywords: ["PFND3DDDI_RESOLVESHAREDRESOURCE callback function"]
ms.keywords: PFND3DDDI_RESOLVESHAREDRESOURCE, PFND3DDDI_RESOLVESHAREDRESOURCE callback, ResolveSharedResource, ResolveSharedResource callback function [Display Devices], UserModeDisplayDriver_Functions_d1818521-a7ef-4daf-8bd7-47103bba2755.xml, d3dumddi/ResolveSharedResource, display.resolvesharedresource
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: ResolveSharedResource is supported beginning with the Windows 7 operating system.
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
req.typenames: 
f1_keywords:
 - "d3dumddi/ResolveSharedResource"
 - "ResolveSharedResource"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - ResolveSharedResource
product:
 - Windows
---

# PFND3DDDI_RESOLVESHAREDRESOURCE callback function

## -description

The <i>ResolveSharedResource</i> function informs a user-mode display driver that ownership of a shared surface changed or that a surface is being used for GDI interoperation.

## -parameters

### -param hDevice

A handle to the display device (that is, the graphics context) that is associated with the shared surface or GDI interoperable surface.

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_resolvesharedresource">D3DDDIARG_RESOLVESHAREDRESOURCE</a> structure that contains a handle to the surface.

## -returns

<i>ResolveSharedResource</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The resource is successfully resolved.|
|D3DDDIERR_DEVICEREMOVED|The driver detects that the graphics adapter was removed. Therefore, the driver did not complete the operation. If the driver never notices the adapter-removal condition, the driver is not required to return this error code.|

## -remarks

The Direct3D runtime calls <i>ResolveSharedResource</i> when an application calls one of the following functions:

<ul>
<li>
<b>IDXGIKeyedMutex::ReleaseSynch</b> on a synchronized shared surface 

</li>
<li>
<b>IDXGISurface1::GetDC</b> for a GDI interoperable surface 

</li>
</ul>
The runtime calls the driver's <i>ResolveSharedResource</i> function every time a shared surface owner changes or when a surface is used for GDI interoperation. The runtime supplies <i>ResolveSharedResource</i> with handles to the display device--via the <i>hDevice</i> parameter-- and the surface--via the <i>pData</i> parameter.

The driver implements <i>ResolveSharedResource</i> to appropriately manage resources for multiple GPU scenarios. Each resource might be divided across memory for multiple GPUs to render on. The driver can implement <i>ResolveSharedResource</i> to remerge each resource so that the new resource owner has the merged resource. The driver must flush any partially built command buffers that might modify the resource.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_resolvesharedresource">D3DDDIARG_RESOLVESHAREDRESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

