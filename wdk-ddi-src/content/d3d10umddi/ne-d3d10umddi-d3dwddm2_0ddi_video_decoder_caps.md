---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_VIDEO_DECODER_CAPS
title: D3DWDDM2_0DDI_VIDEO_DECODER_CAPS (d3d10umddi.h)
description: Describes the video decoder capabilities.
old-location: display\d3dwddm2_0ddi_video_decoder_caps.htm
ms.assetid: 1C3E07CB-917D-4B3E-979D-4DBD38957B98
ms.date: 05/10/2018
keywords: ["D3DWDDM2_0DDI_VIDEO_DECODER_CAPS enumeration"]
ms.keywords: D3DWDDM2_0DDI_VIDEO_DECODER_CAPS, D3DWDDM2_0DDI_VIDEO_DECODER_CAPS enumeration [Display Devices], D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE, D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE_REQUIRED, D3DWDDM2_0DDI_VIDEO_DECODER_CAP_NON_REAL_TIME, D3DWDDM2_0DDI_VIDEO_DECODER_CAP_UNSUPPORTED, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAPS, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE_REQUIRED, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAP_NON_REAL_TIME, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAP_UNSUPPORTED, display.d3dwddm2_0ddi_video_decoder_caps
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: Direct3D 12.0
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
req.typenames: D3DWDDM2_0DDI_VIDEO_DECODER_CAPS
f1_keywords:
 - D3DWDDM2_0DDI_VIDEO_DECODER_CAPS
 - d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3DWDDM2_0DDI_VIDEO_DECODER_CAPS
---

# D3DWDDM2_0DDI_VIDEO_DECODER_CAPS enumeration


## -description

Describes the video decoder capabilities.

## -enum-fields

### -field D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE

Indicates that the driver can support at least some downsampling scenarios.

### -field D3DWDDM2_0DDI_VIDEO_DECODER_CAP_NON_REAL_TIME

The decode operation is supported, but cannot be performed real-time.  Indicates that the decode hardware cannot support the decode operation in real-time. Decode is still viable for transcode scenarios. 



It is possible that decode can occur in real-time if downsampling is applied.

### -field D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE_REQUIRED

	Indicates that the decode configuration can be supported only if down sampling is applied.

### -field D3DWDDM2_0DDI_VIDEO_DECODER_CAP_UNSUPPORTED

	Indicates that the decode configuration is not supported.

## -syntax

```c
typedef enum D3DWDDM2_0DDI_VIDEO_DECODER_CAPS
{ 
    D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE           = 0x01,
    D3DWDDM2_0DDI_VIDEO_DECODER_CAP_NON_REAL_TIME        = 0x02,
    D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE_REQUIRED  = 0x04,
    D3DWDDM2_0DDI_VIDEO_DECODER_CAP_UNSUPPORTED          = 0x08
} D3DWDDM2_0DDI_VIDEO_DECODER_CAPS;
```

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities">QueryVideoCapabilities</a>