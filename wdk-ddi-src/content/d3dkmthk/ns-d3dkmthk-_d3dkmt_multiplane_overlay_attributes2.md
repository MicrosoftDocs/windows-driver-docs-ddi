---
UID: NS:d3dkmthk._D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES2
title: _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES2 (d3dkmthk.h)
description: Contains multiplane overlay attributes.
ms.assetid: 714822e6-9f3c-432c-8584-3f3d61d87dcc
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dkmthk/_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES2"
ms.keywords: _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES2, D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES2, 
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
req.typenames: D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES2
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES2
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES2 structure

## -description

Contains multiplane overlay attributes.

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

### -field VideoFrameFormat
 
### -field ColorSpace

The color space of the data. 

### -field StereoFormat

Stereo format.

### -field StereoLeftViewFrame0

Stereo left view frame 0.

### -field StereoBaseViewFrame0

Stereo base view frame 0.

### -field StereoFlipMode

Stereo flip mode.

### -field StretchQuality

Stretch quality.
 
### -field Reserved1
 
Reserved for internal use.

## -remarks

## -see-also
