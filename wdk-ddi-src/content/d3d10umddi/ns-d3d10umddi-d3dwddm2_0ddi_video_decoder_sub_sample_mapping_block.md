---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK
title: D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK
author: windows-driver-content
description: D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK is used with VideoDecoderSubmitBuffers1 to describe the decoder buffer sub sample mapping block size.
old-location: display\d3dwddm2_0ddi_video_decoder_sub_sample_mapping_block.htm
old-project: display
ms.assetid: FDB38644-AC61-401A-97E2-7CB0ED1C33D4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dwddm2_0ddi_video_decoder_sub_sample_mapping_block, D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK, D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK
---

# D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK structure


## -description


<b>D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK</b> is used with  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecodersubmitbuffers1.md">VideoDecoderSubmitBuffers1</a> to describe the decoder buffer sub sample mapping block size.


## -syntax


````
typedef struct D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK {
  UINT ClearSize;
  UINT EncryptedSize;
} D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK;
````


## -struct-fields




### -field ClearSize

The number of clear (non-encrypted) bytes at the start of the block.


### -field EncryptedSize

The number of encrypted bytes following the clear bytes.


## -remarks


Values in the sub sample mapping blocks are relative to the start of the decode buffer.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecodersubmitbuffers1.md">VideoDecoderSubmitBuffers1</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

