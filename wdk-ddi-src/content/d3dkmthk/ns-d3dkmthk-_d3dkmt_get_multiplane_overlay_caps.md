---
UID: NS:d3dkmthk._D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS
title: _D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS (d3dkmthk.h)
description: Used to get multiplane overlay capabilities.
ms.date: 10/19/2018
keywords: ["D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS structure"]
ms.keywords: _D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS, D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS,
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
req.typenames: D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS
 - d3dkmthk/_D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS
 - D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS
 - d3dkmthk/D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS
 - D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS
dev_langs:
 - c++
---

# _D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS structure


## -description

Used to get multiplane overlay capabilities.

## -struct-fields

### -field hAdapter [in]

A handle to the graphics adapter.

### -field VidPnSourceId [in]

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field MaxPlanes [out]

The total number of planes currently supported.

### -field MaxRGBPlanes [out]

The number of RGB planes currently supported.

### -field MaxYUVPlanes [out]

The number of YUV planes currently supported.

### -field OverlayCaps [out]

Overlay capabilities.

### -field MaxStretchFactor [out]

The maximum stretch factor.

### -field MaxShrinkFactor [out]

 
The maximum shrink factor.

## -remarks

## -see-also

