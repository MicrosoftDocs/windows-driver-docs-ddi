---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY (d3d10umddi.h)
description: Describes the video capabilities to query.
ms.date: 12/09/2022
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

A **D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY** value describes the video capabilities being queried through a call to the driver's [**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md) function.

## -enum-fields

### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING:2

Query the driver's support for the specified down sampling parameters.

### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING:3

Query the driver's support for the specified down sampling parameters recommended by the user-mode driver.

### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS:4

Query the driver's video decoder capabilities.

### -field D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT:5

Query the driver's support for the specified down sample output format.

### -field D3DWDDM2_4DDI_VIDEO_CAPABILITY_QUERY_DECODER_HISTOGRAM:6

Query the driver's support for the specified decoder histogram.

## -see-also

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_caps.md)

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsample_output_format.md)

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling.md)

[**D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM**](ns-d3d10umddi-d3dwddm2_4ddi_video_capability_decoder_histogram.md)

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling.md)

[**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md)
