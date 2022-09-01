---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS
title: PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS (d3d10umddi.h)
description: "The PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS callback function submits one or more video frame buffers for DirectX Video Acceleration (DXVA) decoding."
old-location: display\videodecodersubmitbuffers.htm
ms.date: 08/31/2022
keywords: ["PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS callback function"]
ms.keywords: PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS, PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS callback, d3d10umddi/pfnVideoDecoderSubmitBuffers, display.videodecodersubmitbuffers, pfnVideoDecoderSubmitBuffers, pfnVideoDecoderSubmitBuffers callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS
 - d3d10umddi/PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS
---

# PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS callback function

## -description

Submits one or more video frame buffers for DirectX Video Acceleration (DXVA) decoding.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*hDecoder* [in]

A handle to the video decoder object that was created through a call to the [**CreateVideoDecoder**](nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md) function.

### -param unnamedParam3

**BufferCount** [in]

The number of buffers in the array that is referenced by the **pBufferDesc** parameter.

### -param unnamedParam4

**pBufferDesc** [in]

A pointer to an array of one or more  [**D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC**](ns-d3d10umddi-d3d11_1ddi_video_decoder_buffer_desc.md) structures. For more information, see the Remarks section.

## -returns

**VideoDecoderSubmitBuffers** returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The video buffers were submitted successfully.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -remarks

The **pBufferDesc** parameter points to an array of one or more [**D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC**](ns-d3d10umddi-d3d11_1ddi_video_decoder_buffer_desc.md) structures. Each element in the array describes a compressed video frame buffer that is submitted for decoding.

Each [**D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC**](ns-d3d10umddi-d3d11_1ddi_video_decoder_buffer_desc.md) structure includes the following data:

* The resource that will receive the decrypted and decode frame buffers.

* A [D3D11_1DDI_ENCRYPTED_BLOCK_INFO](./ns-d3d10umddi-d3d11_1ddi_encrypted_block_info.md)  structure that specifies which bytes of the frame buffer are encrypted.

* A pointer to a [D3D11_1DDI_AES_CTR_IV](./ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv.md)  structure that contains an initialization vector (IV) for the frame buffer data that was encrypted by using the 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher encryption algorithm.

> [!NOTE]
> If the decode buffer does not contain any encrypted data, this pointer is set to NULL.

> [!NOTE]
> This function does not honor a Microsoft Direct3D 11 predicate that may have been set.

## -see-also

[**CreateVideoDecoder**](nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md)

[**D3D11_1DDI_AES_CTR_IV**](ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv.md)

[**D3D11_1DDI_ENCRYPTED_BLOCK_INFO**](ns-d3d10umddi-d3d11_1ddi_encrypted_block_info.md)

[**D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC**](ns-d3d10umddi-d3d11_1ddi_video_decoder_buffer_desc.md)
