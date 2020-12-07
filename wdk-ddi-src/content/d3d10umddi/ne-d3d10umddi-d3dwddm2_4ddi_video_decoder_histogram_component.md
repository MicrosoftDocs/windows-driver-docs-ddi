---
UID: NE:d3d10umddi.D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT
title: D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT (d3d10umddi.h)
description: Convenience indices for arrays of per component histogram information.
ms.date: 10/19/2018
keywords: ["D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT enumeration"]
ms.keywords: D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT, D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT,
req.header: d3d10umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT
targetos: Windows
tech.root: display
f1_keywords:
 - D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT
 - d3d10umddi/D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT
topic_type:
 - apiref
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT
product:
 - Windows
---

# D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT enumeration


## -description

Convenience indices for arrays of per component histogram information.

## -enum-fields

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_Y

If the format is a YUV format, indicates a histogram for the Y component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_U

If the format is a YUV format, indicates a histogram for the U component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_V

If the format is a YUV format, indicates a histogram for the V component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_R

If the format is a RGB/BGR format, indicates a histogram for the R component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_G

If the format is a RGB/BGR format, indicates a histogram for the G component.

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_B

If the format is a RGB/BGR format, indicates a histogram for the B component

### -field D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_A

If the format has an alpha channel, indicates a histogram for the A component

## -syntax

```cpp
typedef enum D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT
{
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_Y = 0,
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_U = 1,
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_V = 2,

    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_R = 0,
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_G = 1,
    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_B = 2,

    D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_A = 3,
} D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT;
```

## -remarks

## -see-also

[D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM_COMPONENT_FLAGS enumeration](ne-d3d10umddi-d3dwddm2_4ddi_video_decoder_histogram_component_flags.md)

