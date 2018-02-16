---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
author: windows-driver-content
description: Describes the video capabilities to query.
old-location: display\d3dwddm2_0ddi_video_capability_query.htm
old-project: display
ms.assetid: A8BA3FF9-A821-43ED-91CB-EECD0ABA0954
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS, D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS, D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING, D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING, D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY enumeration [Display Devices], display.d3dwddm2_0ddi_video_capability_query
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY enumeration


## -description


Describes the video capabilities to query.


## -syntax


````
typedef enum D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY { 
  D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS                    = 1,
  D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING            = 2,
  D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING  = 3
} D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY;
````


## -enum-fields




### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING

Indicates that the driver should return support for the specified down sampling parameters specified.



The input structure is of type <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</a>.


### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING

Indicates that the driver should recommend down sampling parameters.



The input structure is of type <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</a>.


### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS

Indicates that the driver should return video decoder capabilities.



The input structure is of type <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_caps.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS</a>.



### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_caps.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

