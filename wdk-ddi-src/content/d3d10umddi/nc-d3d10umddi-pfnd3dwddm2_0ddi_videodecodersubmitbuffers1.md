---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1
title: PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1
author: windows-driver-content
description: VideoDecoderSubmitBuffers1 submits one or more buffers for decoding.
old-location: display\videodecodersubmitbuffers1.htm
old-project: display
ms.assetid: 708A7F64-F8A8-4D0B-A824-CC8DD158216A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1, d3d10umddi/pfnVideoDecoderSubmitBuffers1, display.videodecodersubmitbuffers1, pfnVideoDecoderSubmitBuffers1, pfnVideoDecoderSubmitBuffers1 callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnVideoDecoderSubmitBuffers1
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1 callback


## -description


<b>VideoDecoderSubmitBuffers1</b> submits one or more buffers for decoding.


## -prototype


````
PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1 pfnVideoDecoderSubmitBuffers1;

typedef HRESULT APIENTRY* pfnVideoDecoderSubmitBuffers1(
  _In_       D3D10DDI_HDEVICE                         hDevice,
  _In_       D3D11_1DDI_HDECODE                       hDecode,
  _In_       UINT                                     BufferCount,
  _In_ const D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1 *pBufferDesc
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hDecode [in]

A handle to the video decoder object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a>DDI. 


### -param BufferCount [in]

The number of buffers in the array that is referenced by the <b>pBufferDesc</b> member.


### -param *pBufferDesc [in]

A pointer to an array of one or more <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_buffer_desc1.md">D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</a> structures. 


## -returns




      Returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
Private driver data was successfully returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.


</td>
</tr>
</table>
 




## -remarks



The <b>pBufferDesc</b> member points to an array of one or more <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_buffer_desc1.md">D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</a> structures. Each element in the array describes a compressed video frame buffer that is submitted for decoding. 




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_buffer_desc1.md">D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1 callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

