---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1
title: D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1
author: windows-driver-content
description: D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1 is used with VideoDecoderSubmitBuffers1 to submit one or more buffer for decoding.
old-location: display\d3dwddm2_0ddi_video_decoder_buffer_desc1.htm
old-project: display
ms.assetid: BF57E573-852E-4784-8E76-B5E7D86A57EB
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1, D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1 structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1, display.d3dwddm2_0ddi_video_decoder_buffer_desc1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1
product:
- Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1
---

# D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1 structure


## -description


<b>D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</b> is used with  <a href="https://msdn.microsoft.com/library/windows/hardware/dn906377">VideoDecoderSubmitBuffers1</a> to submit one or more buffer for decoding.


## -struct-fields




### -field hResource

A handle to the resource object that was created through a call to <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>.


### -field BufferType

The type of buffer, specified as a member of the <b>D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE</b> enumeration.


### -field DataOffset

The offset of the relevant data from the beginning of the buffer, in bytes. 

<div class="alert"><b>Important</b>  This value must be zero.</div>
<div> </div>

### -field DataSize

Size of the relevant data.


### -field pIV

A pointer to a buffer that contains an initialization vector (IV) for encrypted data. If the decode buffer does not contain encrypted data, set this member to <b>NULL</b>.


### -field IVSize

The size of the buffer specified in the <b>pIV</b> member. If <b>pIV</b> is <b>NULL</b>, set this member to zero.


### -field pSubSampleMappingBlock

A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/dn894621">D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK</a> structures, which indicate exactly which bytes in the decode buffer are encrypted and which are in the clear.  If the decode buffer does not contain encrypted data, set this member to <b>NULL</b>.



Values in the sub sample mapping blocks are relative to the start of the decode buffer.



### -field SubSampleMappingCount

The number of <a href="https://msdn.microsoft.com/library/windows/hardware/dn894621">D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK</a> structures specified in the <b>pSubSampleMappingBlocks</b> member. If <b>pSubSampleMappingBLocks</b> is <b>NULL</b>, set this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn894621">D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK</a>
 

 

