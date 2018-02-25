---
UID: NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
title: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
author: windows-driver-content
description: Identifies a blend operation to be performed on an overlay plane.
old-location: display\dxgi_ddi_multiplane_overlay_blend.htm
old-project: display
ms.assetid: 00b263e7-8655-4219-8e06-e0feba659d04
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, B, D, DXGI_DDI_MULTIPLANE_OVERLAY_BLEND, DXGI_DDI_MULTIPLANE_OVERLAY_BLEND enumeration [Display Devices], DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND, DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE, E, G, I, L, M, N, O, P, R, T, U, V, X, Y, _, display.dxgi_ddi_multiplane_overlay_blend, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_BLEND, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dxgiddi.h
apiname:
-	DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
---

# DXGI_DDI_MULTIPLANE_OVERLAY_BLEND enumeration


## -description


Identifies a blend operation to be performed on an overlay plane.


## -syntax


````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_BLEND { 
  DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE      = 0x0,
  DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND  = 0x1
} DXGI_DDI_MULTIPLANE_OVERLAY_BLEND;
````


## -enum-fields




### -field DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE

The overlay plane should ignore data in the alpha channel and make the blended plane entirely opaque.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND

The overlay plane should use the pre-multiplied alpha channel in this plane to blend it with the plane beneath.

