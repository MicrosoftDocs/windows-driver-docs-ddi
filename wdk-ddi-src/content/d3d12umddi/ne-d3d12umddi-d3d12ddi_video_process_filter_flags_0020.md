---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020
title: D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020 (d3d12umddi.h)
description: Defines the image filter capabilities for a video processor.
old-location: display\d3d12ddi_video_process_filter_flags.htm
ms.assetid: 28662E87-F6A4-42B0-9BF0-49A6C65B245C
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020, D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020 enumeration [Display Devices], D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_ANAMORPHIC_SCALING, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_BRIGHTNESS, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_CONTRAST, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_EDGE_ENHANCEMENT, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_HUE, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NOISE_REDUCTION, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NONE, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_SATURATION, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_STEREO_ADJUSTMENT, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_ANAMORPHIC_SCALING, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_BRIGHTNESS, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_CONTRAST, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_EDGE_ENHANCEMENT, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_HUE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NOISE_REDUCTION, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_SATURATION, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_STEREO_ADJUSTMENT, display.d3d12ddi_video_process_filter_flags
ms.topic: enum
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020
---

# D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020 enumeration


## -description


Defines the image filter capabilities for a video processor.


## -enum-fields




### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NONE

No flag set.

### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_BRIGHTNESS

The video processor can adjust the brightness level.


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_CONTRAST

The video processor can adjust the contrast level.


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_HUE

The video processor can adjust hue.


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_SATURATION

The video processor can adjust the saturation level.


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NOISE_REDUCTION

The video processor can perform noise reduction.


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_EDGE_ENHANCEMENT

The video processor can perform edge enhancement.


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_ANAMORPHIC_SCALING

The video processor can perform anamorphic scaling. Anamorphic scaling can be used to stretch content with a 4:3 aspect ratio, to a widescreen 16:9 aspect ratio.


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_STEREO_ADJUSTMENT

For stereo 3D video, the video processor can adjust the offset between the left and right views. This allows the user to reduce potential eye strain.


## -remarks



Note that brightness, hue, contrast and saturation support are always supported. These capability flags indicate support for the image filters defined by the [D3D12DDI_VIDEO_PROCESS_FILTER](ne-d3d12umddi-d3d12ddi_video_process_filter_0020.md) enumeration. To apply a particular filter, call the [SetInputStreamFilter](../d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamfilter.md) method.




## -see-also




[D3D12DDI_VIDEO_PROCESS_FILTER enumeration](ne-d3d12umddi-d3d12ddi_video_process_filter_0020.md)
 

 

