---
UID: NC:d3dumddi.PFND3DDDI_SETVIDEOPROCESSRENDERTARGET
title: PFND3DDDI_SETVIDEOPROCESSRENDERTARGET
author: windows-driver-content
description: The SetVideoProcessRenderTarget function sets the render target surface that is used for video processing.
old-location: display\setvideoprocessrendertarget.htm
old-project: display
ms.assetid: 8aa7e23e-f52e-4252-9f22-56ce523f6cba
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
req.alt-api: SetVideoProcessRenderTarget
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

# PFND3DDDI_SETVIDEOPROCESSRENDERTARGET callback



## -description
The <i>SetVideoProcessRenderTarget</i> function sets the render target surface that is used for video processing.



## -prototype

````
PFND3DDDI_SETVIDEOPROCESSRENDERTARGET SetVideoProcessRenderTarget;

__checkReturn HRESULT APIENTRY SetVideoProcessRenderTarget(
  _In_       HANDLE                                hDevice,
  _In_ const D3DDDIARG_SETVIDEOPROCESSRENDERTARGET *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setvideoprocessrendertarget.md">D3DDDIARG_SETVIDEOPROCESSRENDERTARGET</a> structure that describes the render target surface that is used for video processing.


## -returns
<i>SetVideoProcessRenderTarget</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The render target surface is successfully set.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>SetVideoProcessRenderTarget</i> could not allocate the required memory for it to complete.

 


## -remarks
<i>SetVideoProcessRenderTarget</i> can be called only outside of a <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessbeginframe.md">VideoProcessBeginFrame</a>/<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessendframe.md">VideoProcessEndFrame</a> block. 

All video processing render targets are created by setting the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_resourceflags.md">D3DDDI_RESOURCEFLAGS</a>.<b>VideoProcessRenderTarget</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function. 


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setvideoprocessrendertarget.md">D3DDDIARG_SETVIDEOPROCESSRENDERTARGET</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_resourceflags.md">D3DDDI_RESOURCEFLAGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETVIDEOPROCESSRENDERTARGET callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

