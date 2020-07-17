---
UID: NS:d3dkmthk.D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES
title: D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES (d3dkmthk.h)
description: Structure that contains multiplane overlay attributes.
ms.assetid: bb4ee0ea-4045-427d-9229-01c2356bc8ef
ms.date: 10/19/2018
keywords: ["D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES structure"]
f1_keywords:
 - "d3dkmthk/D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES"
 - "D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES"
ms.keywords: D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES, D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES structure

## -description

Structure that contains multiplane overlay attributes.

## -struct-fields

### -field Flags

Flag options.

### -field SrcRect

Specifies the source rectangle.

### -field DstRect

Specifies the destination rectangle.

### -field ClipRect

Specifies any additional clipping.

### -field Rotation

Specifies the clockwise rotation of the overlay plane.

### -field Blend

Specifies the blend mode that applies to this overlay plane and the plane beneath it.

### -field DirtyRectCount

The number of dirty rectangles.

### -field pDirtyRects

A pointer to an array of dirty rectangles.

### -field NumFilters

Optionally specifies the number of filters that the driver and hardware implement on the overlay plane.

### -field pFilters

An optional pointer to a buffer that specifies the filters that the driver and hardware implement on the overlay plane.

### -field VideoFrameFormat

Specifies the overlay plane's video frame format, given as a value from the [D3DKMT_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT](ne-d3dkmthk-d3dkmt_multiplane_overlay_video_frame_format.md) enumeration.

### -field YCbCrFlags

Specifies YUV range and conversion info given as a value from the [D3DKMT_MULTIPLANE_OVERLAY_YCbCr_FLAGS](ne-d3dkmthk-d3dkmt_multiplane_overlay_ycbcr_flags.md) enumeration.

### -field StereoFormat

Specifies the overlay plane's video frame format, given as a value from the [D3DKMT_MULTIPLANE_OVERLAY_STEREO_FORMAT](ne-d3dkmthk-d3dkmt_multiplane_overlay_stereo_format.md) enumeration.

### -field StereoLeftViewFrame0

Reserved for system use. Must always be **FALSE**.

### -field StereoBaseViewFrame0

Reserved for system use. Must always be **FALSE**.

### -field StereoFlipMode

Specifies the overlay plane's stereo flip mode, given as a value from the [_DXGKMT_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE](ne-d3dkmthk-_dxgkmt_multiplane_overlay_stereo_flip_mode.md) enumeration.

### -field StretchQuality
 
Specifies the overlay plane's stretch quality, given as a value from the [_DXGKMT_MULTIPLANE_OVERLAY_STRETCH_QUALITY](ne-d3dkmthk-_dxgkmt_multiplane_overlay_stretch_quality.md) enumeration.

## -remarks

## -see-also
