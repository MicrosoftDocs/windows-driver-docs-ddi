---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS
title: PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS (d3d10umddi.h)
description: Submits one or more video frame buffers for DirectX Video Acceleration (DXVA) decoding.
old-location: display\videodecodersubmitbuffers.htm
ms.assetid: fc1644d8-9058-4100-8e3e-f4727af89773
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS, PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS callback, d3d10umddi/pfnVideoDecoderSubmitBuffers, display.videodecodersubmitbuffers, pfnVideoDecoderSubmitBuffers, pfnVideoDecoderSubmitBuffers callback function [Display Devices]
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnVideoDecoderSubmitBuffers
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS callback function


## -description


Submits one or more video frame buffers for DirectX Video Acceleration (DXVA) decoding.




## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDecoder* [in]

A handle to the video decoder object that was created through a call to the <a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a> function.

### -param Arg3

*BufferCount* [in]

The number of buffers in the array that is referenced by the <i>pBufferDesc</i> parameter.

### -param *

*pBufferDesc* [in]

A pointer to an array of one or more  <a href="https://msdn.microsoft.com/library/windows/hardware/hh698264">D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC</a> structures. For more information, see the Remarks section.




## -returns



<b>VideoDecoderSubmitBuffers</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The video buffers were submitted successfully.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -remarks



The <i>pBufferDesc</i> parameter points to an array of one or more  <a href="https://msdn.microsoft.com/library/windows/hardware/hh698264">D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC</a> structures. Each element in the array describes a compressed video frame buffer that is submitted for decoding.


Each <a href="https://msdn.microsoft.com/library/windows/hardware/hh698264">D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC</a> structure includes the following data:

* The resource that will receive the decrypted and decode frame buffers.

* A [D3D11_1DDI_ENCRYPTED_BLOCK_INFO](https://msdn.microsoft.com/library/windows/hardware/hh406446)  structure that specifies which bytes of the frame buffer are encrypted.

* A pointer to a [D3D11_1DDI_AES_CTR_IV](https://msdn.microsoft.com/library/windows/hardware/hh406334)  structure that contains an initialization vector (IV) for the frame buffer data that was encrypted by using the 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher encryption algorithm.

> [!NOTE]
> If the decode buffer does not contain any encrypted data, this pointer is set to NULL.

> [!NOTE]
> This function does not honor a Microsoft Direct3D 11 predicate that may have been set.


## -see-also




<a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406334">D3D11_1DDI_AES_CTR_IV</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406446">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698264">D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC</a>
 

 

