---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS
author: windows-driver-content
description: Identifies video processor capabilities that the user-mode driver supports.
old-location: display\d3d11_1ddi_video_processor_filter_caps.htm
old-project: display
ms.assetid: ac94ffe8-efab-4b30-8106-f6fed9b59615
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS
req.alt-loc: D3d10umddi.h
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
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS enumeration



## -description
Identifies video processor capabilities that the user-mode driver supports.



## -syntax

````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS { 
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_BRIGHTNESS          = 0x1,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_CONTRAST            = 0x2,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_HUE                 = 0x4,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_SATURATION          = 0x8,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_NOISE_REDUCTION     = 0x10,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_EDGE_ENHANCEMENT    = 0x20,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_ANAMORPHIC_SCALING  = 0x40,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS_STEREO_ADJUSTMENT   = 0x80
} D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS;
````


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


## -remarks
