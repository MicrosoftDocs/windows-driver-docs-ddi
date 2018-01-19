---
UID: NC:d3dumddi.PFND3DDDI_SETDECODERENDERTARGET
title: PFND3DDDI_SETDECODERENDERTARGET
author: windows-driver-content
description: The SetDecodeRenderTarget function sets the render target surface for decoding operations.
old-location: display\setdecoderendertarget.htm
old-project: display
ms.assetid: d522b0f3-ca9c-4e79-96ad-ea9477858ef4
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
req.alt-api: SetDecodeRenderTarget
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

# PFND3DDDI_SETDECODERENDERTARGET callback



## -description
The <i>SetDecodeRenderTarget</i> function sets the render target surface for decoding operations.



## -prototype

````
PFND3DDDI_SETDECODERENDERTARGET SetDecodeRenderTarget;

__checkReturn HRESULT APIENTRY SetDecodeRenderTarget(
  _In_       HANDLE                          hDevice,
  _In_ const D3DDDIARG_SETDECODERENDERTARGET *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setdecoderendertarget.md">D3DDDIARG_SETDECODERENDERTARGET</a> structure that describes the decode render target surface.


## -returns
<i>SetDecodeRenderTarget</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The render target surface is successfully set.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>SetDecodeRenderTarget</i> could not allocate the required memory for it to complete.

 


## -remarks
The <i>SetDecodeRenderTarget</i> function can be called only outside of a <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>/<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeendframe.md">DecodeEndFrame</a> block. 

Decode render targets are always created atomically through calls to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function, where all of the decode buffers are indexes within a single resource. All decode render targets are created by setting the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_resourceflags.md">D3DDDI_RESOURCEFLAGS</a>.<b>DecodeRenderTarget</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure. 


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setdecoderendertarget.md">D3DDDIARG_SETDECODERENDERTARGET</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_resourceflags.md">D3DDDI_RESOURCEFLAGS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeendframe.md">DecodeEndFrame</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETDECODERENDERTARGET callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

