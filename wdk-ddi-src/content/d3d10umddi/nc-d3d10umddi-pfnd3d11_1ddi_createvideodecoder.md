---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEODECODER
title: PFND3D11_1DDI_CREATEVIDEODECODER
author: windows-driver-content
description: Creates a video decoder object.
old-location: display\createvideodecoder.htm
old-project: display
ms.assetid: 41254f99-1806-428c-8bf3-7e736dbeec84
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateVideoDecoder
req.alt-loc: D3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_CREATEVIDEODECODER callback



## -description
Creates a video decoder object.



## -prototype

````
PFND3D11_1DDI_CREATEVIDEODECODER CreateVideoDecoder;

HRESULT APIENTRY* CreateVideoDecoder(
  _In_       D3D10DDI_HDEVICE                 hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEODECODER *pCreateData,
  _In_       D3D11_1DDI_HDECODE               hDecoder,
  _In_       D3D11_1DDI_HRTDECODE             hRTDecode
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param pCreateData [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a> structure. This structure specifies the attributes of the video decoder object to be created.


### -param hDecoder [in]

A handle to the driver's private data for the video decoder object. For more information, see the Remarks section.


### -param hRTDecode [in]

A handle to the video decoder object that the driver should use when it calls back into the runtime.


## -returns
<b>CreateVideoDecoder</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The video decoder object was created successfully.
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>The graphics adapter was removed.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
        Memory was not available to complete the operation.

 


## -remarks
The Microsoft Direct3D runtime calls <i>CreateVideoDecoder</i> after it has called the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecodersize.md">CalcPrivateVideoDecoderSize</a> to determine the size in bytes for the private data that the driver requires for the video decoder object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video decoder object.

When the runtime  calls <i>CreateVideoDecoder</i>, it passes the handle to the private data memory in the <i>hDecoder</i> parameter. This handle is actually a pointer to the memory. 

The driver must keep track of the handle to the display device that was used to create the cryptographic session. The driver should fail all subsequent calls that use this created cryptographic session, such as <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md">VideoDecoderBeginFrame</a>, if the display device that is specified in those calls is different from the display device that was used to create the video decoder. 




## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecodersize.md">CalcPrivateVideoDecoderSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md">VideoDecoderBeginFrame</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATEVIDEODECODER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

