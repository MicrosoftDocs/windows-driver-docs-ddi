---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK
title: D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK (d3d10umddi.h)
description: D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK is used with VideoDecoderSubmitBuffers1 to describe the decoder buffer sub sample mapping block size.
old-location: display\d3dwddm2_0ddi_video_decoder_sub_sample_mapping_block.htm
ms.assetid: FDB38644-AC61-401A-97E2-7CB0ED1C33D4
ms.date: 05/10/2018
ms.keywords: D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK, D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK, display.d3dwddm2_0ddi_video_decoder_sub_sample_mapping_block
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
-	D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK
---

# D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK structure


## -description


<b>D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK</b> is used with  <a href="https://msdn.microsoft.com/library/windows/hardware/dn906377">VideoDecoderSubmitBuffers1</a> to describe the decoder buffer sub sample mapping block size.


## -struct-fields




### -field ClearSize

The number of clear (non-encrypted) bytes at the start of the block.


### -field EncryptedSize

The number of encrypted bytes following the clear bytes.


## -remarks



Values in the sub sample mapping blocks are relative to the start of the decode buffer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906377">VideoDecoderSubmitBuffers1</a>
 

 

