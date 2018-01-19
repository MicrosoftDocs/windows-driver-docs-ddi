---
UID: NC:d3dumddi.PFND3DDDI_RESOLVESHAREDRESOURCE
title: PFND3DDDI_RESOLVESHAREDRESOURCE
author: windows-driver-content
description: The ResolveSharedResource function informs a user-mode display driver that ownership of a shared surface changed or that a surface is being used for GDI interoperation.
old-location: display\resolvesharedresource.htm
old-project: display
ms.assetid: 8ad9130e-bade-4fd2-b345-b6361fd001ef
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: ResolveSharedResource is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ResolveSharedResource
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_RESOLVESHAREDRESOURCE callback



## -description
The <i>ResolveSharedResource</i> function informs a user-mode display driver that ownership of a shared surface changed or that a surface is being used for GDI interoperation. 



## -prototype

````
PFND3DDDI_RESOLVESHAREDRESOURCE ResolveSharedResource;

__checkReturn HRESULT APIENTRY ResolveSharedResource(
  _In_       HANDLE                          hDevice,
  _In_ const D3DDDIARG_RESOLVESHAREDRESOURCE *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (that is, the graphics context) that is associated with the shared surface or GDI interoperable surface. 


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_resolvesharedresource.md">D3DDDIARG_RESOLVESHAREDRESOURCE</a> structure that contains a handle to the surface. 


## -returns
<i>ResolveSharedResource</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The resource is successfully resolved.
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>The driver detects that the graphics adapter was removed. Therefore, the driver did not complete the operation. If the driver never notices the adapter-removal condition, the driver is not required to return this error code. 

 


## -remarks
The Direct3D runtime calls <i>ResolveSharedResource</i> when an application calls one of the following functions:

<b>IDXGIKeyedMutex::ReleaseSynch</b> on a synchronized shared surface 

<b>IDXGISurface1::GetDC</b> for a GDI interoperable surface 

The runtime calls the driver's <i>ResolveSharedResource</i> function every time a shared surface owner changes or when a surface is used for GDI interoperation. The runtime supplies <i>ResolveSharedResource</i> with handles to the display device--via the <i>hDevice</i> parameter-- and the surface--via the <i>pData</i> parameter.

The driver implements <i>ResolveSharedResource</i> to appropriately manage resources for multiple GPU scenarios. Each resource might be divided across memory for multiple GPUs to render on. The driver can implement <i>ResolveSharedResource</i> to remerge each resource so that the new resource owner has the merged resource. The driver must flush any partially built command buffers that might modify the resource.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_resolvesharedresource.md">D3DDDIARG_RESOLVESHAREDRESOURCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_RESOLVESHAREDRESOURCE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

