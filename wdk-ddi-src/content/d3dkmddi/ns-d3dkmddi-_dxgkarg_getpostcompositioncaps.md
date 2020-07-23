---
UID: NS:d3dkmddi._DXGKARG_GETPOSTCOMPOSITIONCAPS
title: _DXGKARG_GETPOSTCOMPOSITIONCAPS (d3dkmddi.h)
description: Arguments for the DxgkDdiGetPostCompositionCaps function.
old-location: display\dxgkarg_getpostcompositioncaps.htm
ms.assetid: 0C8A0F83-9D12-46F1-A8B1-3BCF219A3BF7
ms.date: 05/10/2018
keywords: ["_DXGKARG_GETPOSTCOMPOSITIONCAPS structure"]
ms.keywords: "*IN_OUT_PDXGKARG_GETPOSTCOMPOSITIONCAPS, DXGKARG_GETPOSTCOMPOSITIONCAPS, DXGKARG_GETPOSTCOMPOSITIONCAPS structure [Display Devices], _DXGKARG_GETPOSTCOMPOSITIONCAPS, d3dkmddi/DXGKARG_GETPOSTCOMPOSITIONCAPS, display.dxgkarg_getpostcompositioncaps"
f1_keywords:
 - "d3dkmddi/DXGKARG_GETPOSTCOMPOSITIONCAPS"
 - "DXGKARG_GETPOSTCOMPOSITIONCAPS"
req.header: d3dkmddi.h
req.include-header: 
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
- d3dkmddi.h
api_name:
- DXGKARG_GETPOSTCOMPOSITIONCAPS
targetos: Windows
tech.root: display
req.typenames: DXGKARG_GETPOSTCOMPOSITIONCAPS
---

# _DXGKARG_GETPOSTCOMPOSITIONCAPS structure


## -description


Arguments for the DxgkDdiGetPostCompositionCaps function.


## -struct-fields




### -field VidPnSourceId

[in] Indicates the VidPn source for which post composition capabilities are queried.


### -field MaxStretchFactor

[out] Indicates the maximum stretch factor that can be applied.


### -field MaxShrinkFactor

[out] Indicates the maximum shrink factor that can be applied.

