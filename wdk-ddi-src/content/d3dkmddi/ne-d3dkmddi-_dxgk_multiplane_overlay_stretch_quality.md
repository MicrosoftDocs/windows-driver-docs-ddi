---
UID: NE:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY
title: "_DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY"
author: windows-driver-content
description: Identifies filtering processes that the hardware should perform when it stretches or shrinks multiplane overlay data.
old-location: display\dxgk_multiplane_overlay_stretch_quality.htm
old-project: display
ms.assetid: 5C995970-59E4-46AD-84CD-0B5675949308
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH, _DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY, DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR, display.dxgk_multiplane_overlay_stretch_quality, DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY, DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmddi.h
apiname:
-	DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY
---

# _DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY enumeration


## -description


Identifies filtering processes that the hardware should perform when it stretches or shrinks multiplane overlay data.


## -syntax


````
typedef enum _DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY { 
  DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR  = 0x1,
  DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH      = 0x2
} DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY;
````


## -enum-fields




### -field DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR

When the hardware stretches or shrinks the data, it should perform bilinear filtering. If the hardware lacks enough resources to perform bilinear shrinking, the user-mode display driver can use point sampling.


### -field DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH

When the hardware stretches or shrinks the data, it should perform the highest quality filtering that it supports.

