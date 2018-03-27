---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC
title: D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC
author: windows-driver-content
description: Describes a compressed buffer for Microsoft DirectX Video Acceleration (DXVA) decoding.
old-location: display\d3d11_1ddi_video_decoderr_buffer_desc.htm
old-project: display
ms.assetid: aff44ad9-7ade-4b01-8e41-11d686728faa
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC, D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC structure [Display Devices], D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC, D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC, display.d3d11_1ddi_video_decoderr_buffer_desc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC
---

# D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC structure


## -description


Describes a compressed buffer for Microsoft DirectX Video Acceleration (DXVA) decoding.


## -struct-fields




### -field hResource

A handle to the resource that will receive the decrypted and decode frame buffers.


### -field BufferType

The type of buffer, specified as a constant value of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451066">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a> enumeration.

In D3d10umddi.h, <a href="https://msdn.microsoft.com/library/windows/hardware/hh451066">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a> and <b>D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE</b> are defined as the same type.


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

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406334">D3D11_1DDI_AES_CTR_IV</a> structure that contains an initialization vector (IV) for the frame buffer data that was encrypted by using the 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher encryption algorithm.

If the decode buffer does not contain any encrypted data, set <b>pIV</b> to <b>NULL</b>.


### -field IVSize

The size of the buffer specified in the <b>pIV</b> member. If <b>pIV</b> is <b>NULL</b>, set this member to zero.


### -field PartialEncryption

If <b>TRUE</b>, the video surfaces are partially encrypted.


### -field EncryptedBlockInfo

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406446">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a> structure that specifies which bytes of the surface are encrypted.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406334">D3D11_1DDI_AES_CTR_IV</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406446">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451066">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

