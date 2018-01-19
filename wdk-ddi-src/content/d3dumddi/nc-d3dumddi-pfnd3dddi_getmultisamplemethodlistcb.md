---
UID: NC:d3dumddi.PFND3DDDI_GETMULTISAMPLEMETHODLISTCB
title: PFND3DDDI_GETMULTISAMPLEMETHODLISTCB
author: windows-driver-content
description: The pfnGetMultisampleMethodListCb function retrieves a list of multiple-sample methods that are used for the given width, height, and format of an allocation.
old-location: display\pfngetmultisamplemethodlistcb.htm
old-project: display
ms.assetid: 2e3f9ee9-83a0-4b81-a22b-594e5bd4d046
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
req.alt-api: pfnGetMultisampleMethodListCb
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

# PFND3DDDI_GETMULTISAMPLEMETHODLISTCB callback



## -description
The <b>pfnGetMultisampleMethodListCb</b> function retrieves a list of multiple-sample methods that are used for the given width, height, and format of an allocation.



## -prototype

````
PFND3DDDI_GETMULTISAMPLEMETHODLISTCB pfnGetMultisampleMethodListCb;

__checkReturn HRESULT APIENTRY CALLBACK pfnGetMultisampleMethodListCb(
  _In_    HANDLE                            hAdapter,
  _Inout_ D3DDDICB_GETMULTISAMPLEMETHODLIST *pData
)
{ ... }
````


## -parameters

### -param hAdapter [in]

A handle to the graphics adapter object. 


### -param pData [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_getmultisamplemethodlist.md">D3DDDICB_GETMULTISAMPLEMETHODLIST</a> structure that describes the list of multiple-sample methods for an allocation.


## -returns
<b>pfnGetMultisampleMethodListCb</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The list of multiple-sample methods was successfully retrieved.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other HRESULT values.


## -remarks
The user-mode display driver typically uses the <b>pfnGetMultisampleMethodListCb</b> function with its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>, or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a> function and the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function. The driver uses <b>pfnGetMultisampleMethodListCb</b> when the Direct3D runtime calls the driver's <i>CreateResource</i>, <i>CreateResource(D3D10)</i>, or <i>CreateResource(D3D11)</i> to request that the driver create a multiple-sampled primary. The driver also uses <b>pfnGetMultisampleMethodListCb</b> when it must perform multiple-sampling while scanning out from the primary. This type of multiple-sampling might consume additional memory bandwidth, beyond the bandwidth required for scanning out the display mode. Therefore, <b>pfnGetMultisampleMethodListCb</b> queries the display mode manager (DMM) (and indirectly the display miniport driver) to retrieve a list of supported multiple-sampling methods for the given width, height, and format. If <b>pfnGetMultisampleMethodListCb</b> reports that no methods are supported, the user-mode display driver must use a nonscan-out version of multiple-sampling, typically by creating a standard nonmultiple-sampled primary.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_adaptercallbacks.md">D3DDDI_ADAPTERCALLBACKS</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_getmultisamplemethodlist.md">D3DDDICB_GETMULTISAMPLEMETHODLIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_GETMULTISAMPLEMETHODLISTCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

