---
UID: NC:d3dumddi.PFND3DDDI_OPENRESOURCE
title: PFND3DDDI_OPENRESOURCE
author: windows-driver-content
description: The OpenResource function informs the driver that a shared resource is opened.
old-location: display\openresource.htm
old-project: display
ms.assetid: e3f5cec2-391b-40f9-8a4b-afe6b8de2954
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OpenResource
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

# PFND3DDDI_OPENRESOURCE callback



## -description
The <i>OpenResource</i> function informs the driver that a shared resource is opened.



## -prototype

````
PFND3DDDI_OPENRESOURCE OpenResource;

__checkReturn HRESULT APIENTRY OpenResource(
  _In_    HANDLE                 hDevice,
  _Inout_ D3DDDIARG_OPENRESOURCE *pResource
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context) that is used to open the resource.


### -param pResource [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_openresource.md">D3DDDIARG_OPENRESOURCE</a> structure that describes the resource that is opened.


## -returns
<i>OpenResource</i> returns S_OK or an appropriate error result if the resource is not successfully opened.


## -remarks
The Microsoft Direct3D runtime calls the user-mode display driver's <i>OpenResource</i> function to inform the user-mode display driver that a shared resource is opened. The driver should store any information that is required to describe the resource and return a unique handle in the <b>hResource</b> member of the D3DDDIARG_OPENRESOURCE structure (pointed to by the <i>pResource</i> parameter) that identifies the new resource in subsequent calls that the Direct3D runtime makes to the driver. The private driver data that is passed to <i>OpenResource</i> is the same private driver data that was passed to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function when the resource was created.

For more information about creating and destroying resources, see <a href="https://msdn.microsoft.com/d443bdc3-1c5a-4372-9e6a-b8a4d21499b9">Handling Resource Creation and Destruction</a>.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_openresource.md">D3DDDIARG_OPENRESOURCE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_OPENRESOURCE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

