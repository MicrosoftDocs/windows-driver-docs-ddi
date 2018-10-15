---
UID: NE:d3d10umddi.D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS
title: D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS
author: windows-driver-content
description: Flags for indicating a subset of components used with video decode histogram.
ms.assetid: ce69c641-c6ed-45ba-8e4e-2a0e9f0681f0
ms.author: windowsdriverdev
ms.date:
ms.topic: enum
ms.keywords: D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS, D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS,
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d10umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS enumeration

## -description

Flags for indicating a subset of components used with video decode histogram.

## -syntax


```
typedef enum D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS
{
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_NONE = 0x0,
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_Y = (1 << D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_Y),
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_U = (1 << D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_U),
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_V = (1 << D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_V),

    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_R = (1 << D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_R),
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_G = (1 << D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_G),
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_B = (1 << D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_B),

    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_A = (1 << D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_A),

// ;begin_internal
    D3DWDDM2_4DDI_VIDEO_DECODE_HISTOGRAM_COMPONENT_FLAG_MASK = D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_Y
                                                             | D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_U
                                                             | D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_V
                                                             | D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_R
                                                             | D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_G
                                                             | D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_B
                                                             | D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_A,

// ;end_internal
} D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS;
```

## -enum-fields

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_NONE

No associated component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_Y

If the format is a YUV format, indicates the Y component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_U

If the format is a YUV format, indicates the U component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_V

If the format is a YUV format, indicates the V component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_R

If the format is a RGB/BGR format, indicates the Y component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_G

If the format is a RGB/BGR format, indicates the G component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_B

If the format is a RGB/BGR format, indicates the B component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAG_A

If the format has an alpha channel, indicates the A component.

## -remarks

## -see-also

[D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT enumeration](ne-d3d10umddi-d3dwddm2_4ddi_video_decoder_histogram_component.md)