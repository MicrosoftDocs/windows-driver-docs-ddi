---
UID: NS:d3dkmthk._D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3
title: _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 (d3dkmthk.h)
description: Contains multiplane overlay attributes.
ms.assetid: df7e60d8-a1f8-4bca-9e7f-70c575b5cc96
ms.date: 10/19/2018
keywords: ["_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 structure"]
f1_keywords:
 - "d3dkmthk/_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3"
ms.keywords: _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3, D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3, 
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
req.typenames: D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 structure

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

### -field ColorSpace

The color space of the data. 

### -field StretchQuality

Stretch quality.

### -field SDRWhiteLevel
 
SDR (standard dynamic range) white level.

## -remarks

## -see-also
