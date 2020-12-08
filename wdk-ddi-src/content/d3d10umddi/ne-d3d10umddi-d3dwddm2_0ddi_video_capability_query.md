---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY (d3d10umddi.h)
description: Describes the video capabilities to query.
old-location: display\d3dwddm2_0ddi_video_capability_query.htm
ms.date: 05/10/2018
keywords: ["D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY enumeration"]
ms.keywords: D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY, D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY enumeration [Display Devices], D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS, D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING, D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING, display.d3dwddm2_0ddi_video_capability_query
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
targetos: Windows
tech.root: display
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
f1_keywords:
 - D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
 - d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY enumeration


## -description

Describes the video capabilities to query.

## -enum-fields

### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING

Indicates that the driver should return support for the specified down sampling parameters specified.



The input structure is of type <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</a>.

### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING

Indicates that the driver should recommend down sampling parameters.



The input structure is of type <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling">D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</a>.

### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS

Indicates that the driver should return video decoder capabilities.



The input structure is of type <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_caps">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS</a>.

### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT

### -field D3DWDDM2_4DDI_VIDEO_CAPABILITY_QUERY_DECODER_HISTOGRAM

Query driver for decoder histogram support. The associated data structure is D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_caps">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling">D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</a>
