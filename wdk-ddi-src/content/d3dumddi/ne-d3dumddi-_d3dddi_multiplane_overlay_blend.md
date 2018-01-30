---
UID: NE:d3dumddi._D3DDDI_MULTIPLANE_OVERLAY_BLEND
title: "_D3DDDI_MULTIPLANE_OVERLAY_BLEND"
author: windows-driver-content
description: Identifies a blend operation to be performed on an overlay plane.
old-location: display\d3dddi_multiplane_overlay_blend.htm
old-project: display
ms.assetid: 1ee411f2-1779-41bd-808c-40639bb22662
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_BLEND enumeration [Display Devices], D3DDDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_BLEND, display.d3dddi_multiplane_overlay_blend, D3DDDI_MULTIPLANE_OVERLAY_BLEND, D3DDDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND, _D3DDDI_MULTIPLANE_OVERLAY_BLEND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	D3dumddi.h
apiname:
-	D3DDDI_MULTIPLANE_OVERLAY_BLEND
product: Windows
targetos: Windows
req.typenames: D3DDDI_MULTIPLANE_OVERLAY_BLEND
---

# _D3DDDI_MULTIPLANE_OVERLAY_BLEND enumeration


## -description


Identifies a blend operation to be performed on an overlay plane.


## -syntax


````
typedef enum _D3DDDI_MULTIPLANE_OVERLAY_BLEND { 
  D3DDDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE      = 0x0,
  D3DDDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND  = 0x1
} D3DDDI_MULTIPLANE_OVERLAY_BLEND;
````


## -enum-fields




### -field D3DDDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE

The overlay plane should ignore data in the alpha channel and make the blended plane entirely opaque.


### -field D3DDDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND

The overlay plane should use the pre-multiplied alpha channel in this plane to blend it with the plane beneath.

