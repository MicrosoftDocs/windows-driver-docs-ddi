---
UID: NS:d3dkmthk._D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3
title: _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3 (d3dkmthk.h)
description: Check multiplane overlay plane.
ms.assetid: 4d3ffbc5-2d32-417e-bc9e-f1520b1a5234
ms.date: 10/19/2018
keywords: ["_D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3 structure"]
f1_keywords:
 - "d3dkmthk/_D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3"
 - "_D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3"
ms.keywords: _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3, D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3, 
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
req.typenames: D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3 structure

## -description

Check multiplane overlay plane.

## -struct-fields

### -field LayerIndex

The layer index.

### -field hResource

Handle for this resource in this process.

### -field CompSurfaceLuid

The component surface LUID (locally unique identifier).

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field pPlaneAttributes
 
Pointer to a D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 structure that contains the plane attributes.

## -remarks

## -see-also
