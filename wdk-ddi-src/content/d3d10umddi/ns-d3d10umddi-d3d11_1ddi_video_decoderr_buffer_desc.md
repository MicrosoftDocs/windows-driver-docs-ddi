---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC
title: D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC (d3d10umddi.h)
description: Describes a compressed buffer for Microsoft DirectX Video Acceleration (DXVA) decoding.
old-location: display\d3d11_1ddi_video_decoderr_buffer_desc.htm
ms.assetid: aff44ad9-7ade-4b01-8e41-11d686728faa
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC structure"]
ms.keywords: D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC, D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC structure [Display Devices], D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC, D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC, display.d3d11_1ddi_video_decoderr_buffer_desc
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC"
 - "D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
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
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC
---

# D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC structure


## -description


Describes a compressed buffer for Microsoft DirectX Video Acceleration (DXVA) decoding.


## -struct-fields




### -field hResource

A handle to the resource that will receive the decrypted and decode frame buffers.


### -field BufferType

The type of buffer, specified as a constant value of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a> enumeration.

In D3d10umddi.h, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a> and <b>D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE</b> are defined as the same type.


### -field BufferIndex

Reserved for system use.


### -field DataOffset

The offset of the relevant data from the beginning of the buffer, in bytes. This value must be zero.


### -field DataSize

The offset of the relevant data from the beginning of the buffer, in bytes. This value must be zero.


### -field FirstMBaddress

The macroblock address of the first macroblock in the buffer. The macroblock address is given in raster scan order.


### -field NumMBsInBuffer

The number of macroblocks of data in the buffer. This count includes skipped macroblocks.


### -field Width

Reserved for system use. Set to zero.


### -field Height

Reserved for system use. Set to zero.


### -field Stride

Reserved for system use. Set to zero.


### -field ReservedBits

Reserved for system use. Set to zero.


### -field pIV

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv">D3D11_1DDI_AES_CTR_IV</a> structure that contains an initialization vector (IV) for the frame buffer data that was encrypted by using the 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher encryption algorithm.

If the decode buffer does not contain any encrypted data, set <b>pIV</b> to <b>NULL</b>.


### -field IVSize

The size of the buffer specified in the <b>pIV</b> member. If <b>pIV</b> is <b>NULL</b>, set this member to zero.


### -field PartialEncryption

If <b>TRUE</b>, the video surfaces are partially encrypted.


### -field EncryptedBlockInfo

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_encrypted_block_info">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a> structure that specifies which bytes of the surface are encrypted.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv">D3D11_1DDI_AES_CTR_IV</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_encrypted_block_info">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a>
 

 

