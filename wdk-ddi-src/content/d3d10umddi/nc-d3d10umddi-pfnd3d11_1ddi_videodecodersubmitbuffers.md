---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS
title: PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS
author: windows-driver-content
description: Submits one or more video frame buffers for DirectX Video Acceleration (DXVA) decoding.
old-location: display\videodecodersubmitbuffers.htm
old-project: display
ms.assetid: fc1644d8-9058-4100-8e3e-f4727af89773
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videodecodersubmitbuffers, pfnVideoDecoderSubmitBuffers callback function [Display Devices], pfnVideoDecoderSubmitBuffers, PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS, PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS, d3d10umddi/pfnVideoDecoderSubmitBuffers
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
-	D3d10umddi.h
apiname:
-	pfnVideoDecoderSubmitBuffers
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS callback


## -description


Submits one or more video frame buffers for DirectX Video Acceleration (DXVA) decoding.




## -prototype


````
PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS pfnVideoDecoderSubmitBuffers;

HRESULT APIENTRY* pfnVideoDecoderSubmitBuffers(
  _In_       D3D10DDI_HDEVICE                     hDevice,
  _In_       D3D11_1DDI_HDECODE                   hDecoder,
  _In_       UINT                                 BufferCount,
  _In_ const D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC *pBufferDesc
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D11_1DDI_HDECODE



### -param UINT



### -param *






#### - BufferCount [in]

The number of buffers in the array that is referenced by the <i>pBufferDesc</i> parameter.


#### - hDecoder [in]

A handle to the video decoder object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a> function.




#### - hDevice [in]

A handle to the display device (graphics context).




#### - pBufferDesc [in]

A pointer to an array of one or more  <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoderr_buffer_desc.md">D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC</a> structures. For more information, see the Remarks section.


## -returns


<b>VideoDecoderSubmitBuffers</b> returns one of the following values:
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
The video buffers were submitted successfully.

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


The <i>pBufferDesc</i> parameter points to an array of one or more  <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoderr_buffer_desc.md">D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC</a> structures. Each element in the array describes a compressed video frame buffer that is submitted for decoding.


Each <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoderr_buffer_desc.md">D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC</a> structure includes the following data:
<ul>
<li>
The resource that will receive the decrypted and decode frame buffers.

</li>
<li>
A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_encrypted_block_info.md">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a> structure that specifies which bytes of the frame buffer are encrypted.



</li>
<li>
A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv.md">D3D11_1DDI_AES_CTR_IV</a> structure that contains an initialization vector (IV) for the frame buffer data that was encrypted by using the 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher encryption algorithm.

<div class="alert"><b>Note</b>  If the decode buffer does not contain any encrypted data, this pointer is set to NULL.</div>
<div> </div>
</li>
</ul><div class="alert"><b>Note</b>  This function does not honor a Microsoft Direct3D 11 predicate that may have been set.</div><div> </div>


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv.md">D3D11_1DDI_AES_CTR_IV</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoderr_buffer_desc.md">D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_encrypted_block_info.md">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

