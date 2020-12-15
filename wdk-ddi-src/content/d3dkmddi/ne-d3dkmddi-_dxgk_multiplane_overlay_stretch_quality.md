---
UID: NE:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY
title: _DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY (d3dkmddi.h)
description: Identifies filtering processes that the hardware should perform when it stretches or shrinks multiplane overlay data.
old-location: display\dxgk_multiplane_overlay_stretch_quality.htm
ms.date: 05/10/2018
keywords: ["DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY enumeration"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY, DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY enumeration [Display Devices], DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR, DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH, _DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH, display.dxgk_multiplane_overlay_stretch_quality
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY
f1_keywords:
 - _DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY
 - d3dkmddi/_DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY
 - DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY
 - d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY
---

# _DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY enumeration


## -description

Identifies filtering processes that the hardware should perform when it stretches or shrinks multiplane overlay data.

## -enum-fields

### -field DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR

When the hardware stretches or shrinks the data, it should perform bilinear filtering. If the hardware lacks enough resources to perform bilinear shrinking, the user-mode display driver can use point sampling.

### -field DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH

When the hardware stretches or shrinks the data, it should perform the highest quality filtering that it supports.

