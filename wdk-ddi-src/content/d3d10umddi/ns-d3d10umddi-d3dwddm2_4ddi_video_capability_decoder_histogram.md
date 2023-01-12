---
UID: NS:d3d10umddi.D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM
title: D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM (d3d10umddi.h)
description: Data structure for the associated D3DWDDM2_4DDI_VIDEO_CAPABILITY_QUERY_DECODER_HISTOGRAM value in the video capability query D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY enumeration.
ms.date: 12/09/2022
keywords: ["D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM structure"]
ms.keywords: D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM, D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM,
req.header: d3d10umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10 version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM
targetos: Windows
tech.root: display
f1_keywords:
 - D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM
 - d3d10umddi/D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM
product:
 - Windows
---

# D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM structure

## -description

**D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM** describes the video decoder histogram capabilities. The driver provides these capabilities when its [**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md) function is called.

## -struct-fields

### -field DecoderDesc

[in] A [**D3D11_1DDI_VIDEO_DECODER_DESC**](ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md) structure containing the description for the decoder to be used with decode histogram.

### -field Components

[out] A [**D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS**](ne-d3d10umddi-d3dwddm2_4ddi_video_decoder_histogram_component_flags.md) value that specifies the components (or channels) of a DXGI_FORMAT that the hardware supports.

### -field BinCount

[out] The number of per component bins supported. **BinCount** must be >= 64 and must be a power of 2 (64, 128, 256, 512, etc.).

### -field CounterBitDepth

[out] The bit depth of the bin counter. The counter is always stored in a 32-bit value and is therefore 32 bits or less. The counter is stored in the lower bits of the 32 bit storage. The upper bits are set to zero. If the in count exceeds this bit depth, the value is set to the maximum counter value. Valid values for **CounterBitDepth** are 16, 24, and 32.

## -see-also

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY**](ne-d3d10umddi-d3dwddm2_0ddi_video_capability_query.md)

[**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md)
