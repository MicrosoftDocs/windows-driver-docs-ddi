---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS (d3d10umddi.h)
description: Identifies video processor capabilities that the user-mode driver supports.
old-location: display\d3d11_1ddi_video_processor_filter_caps.htm
ms.assetid: ac94ffe8-efab-4b30-8106-f6fed9b59615
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS enumeration"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS enumeration [Display Devices], D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_ANAMORPHIC_SCALING, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_BRIGHTNESS, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_CONTRAST, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_EDGE_ENHANCEMENT, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_HUE, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_NOISE_REDUCTION, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_SATURATION, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_STEREO_ADJUSTMENT, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_ANAMORPHIC_SCALING, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_BRIGHTNESS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_CONTRAST, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_EDGE_ENHANCEMENT, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_HUE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_NOISE_REDUCTION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_SATURATION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_STEREO_ADJUSTMENT, display.d3d11_1ddi_video_processor_filter_caps
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3d10umddi.h
api_name:
- D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS enumeration


## -description


Identifies video processor capabilities that the user-mode driver supports.


## -enum-fields




### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_BRIGHTNESS

Brightness filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_CONTRAST

Contrast filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_HUE

Hue filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_SATURATION

Saturation filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_NOISE_REDUCTION

Noise reduction filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_EDGE_ENHANCEMENT

Edge enhancement filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_ANAMORPHIC_SCALING

Anamorphic scaling filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_STEREO_ADJUSTMENT

Stereo adjustment filter. When stereo 3-D video is enabled, this filter adjusts the offset between the left and right views, allowing the user to reduce potential eye strain.

The filter value indicates the amount by which the left and right views are adjusted. A positive value shifts the images away from each other: the left image toward the left, and the right image toward the right. A negative value shifts the images in the opposite directions, closer to each other.

