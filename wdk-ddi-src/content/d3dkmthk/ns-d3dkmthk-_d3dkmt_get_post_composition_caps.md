---
UID: NS:d3dkmthk._D3DKMT_GET_POST_COMPOSITION_CAPS
title: _D3DKMT_GET_POST_COMPOSITION_CAPS (d3dkmthk.h)
description: Used to get post composition capabilities.
ms.date: 10/19/2018
keywords: ["D3DKMT_GET_POST_COMPOSITION_CAPS structure"]
ms.keywords: _D3DKMT_GET_POST_COMPOSITION_CAPS, D3DKMT_GET_POST_COMPOSITION_CAPS,
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
req.typenames: D3DKMT_GET_POST_COMPOSITION_CAPS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_GET_POST_COMPOSITION_CAPS
 - d3dkmthk/_D3DKMT_GET_POST_COMPOSITION_CAPS
 - D3DKMT_GET_POST_COMPOSITION_CAPS
 - d3dkmthk/D3DKMT_GET_POST_COMPOSITION_CAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_GET_POST_COMPOSITION_CAPS
 - D3DKMT_GET_POST_COMPOSITION_CAPS
dev_langs:
 - c++
---

# _D3DKMT_GET_POST_COMPOSITION_CAPS structure


## -description

Used to get post composition capabilities.

## -struct-fields

### -field hAdapter

A handle to the graphics adapter.

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field MaxStretchFactor

[out] The maximum stretch factor.

### -field MaxShrinkFactor

[out] The maximum shrink factor.

## -remarks

## -see-also

