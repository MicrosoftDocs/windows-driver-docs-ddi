---
UID: NE:d3dumddi._D3DDDI_MULTIPLANE_OVERLAY_BLEND
title: _D3DDDI_MULTIPLANE_OVERLAY_BLEND (d3dumddi.h)
description: Identifies a blend operation to be performed on an overlay plane.
old-location: display\d3dddi_multiplane_overlay_blend.htm
tech.root: display
ms.assetid: 1ee411f2-1779-41bd-808c-40639bb22662
ms.date: 05/10/2018
keywords: ["D3DDDI_MULTIPLANE_OVERLAY_BLEND enumeration"]
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_BLEND, D3DDDI_MULTIPLANE_OVERLAY_BLEND enumeration [Display Devices], D3DDDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND, D3DDDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE, _D3DDDI_MULTIPLANE_OVERLAY_BLEND, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_BLEND, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE, display.d3dddi_multiplane_overlay_blend
f1_keywords:
 - "d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_BLEND"
 - "D3DDDI_MULTIPLANE_OVERLAY_BLEND"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dumddi.h
api_name:
- D3DDDI_MULTIPLANE_OVERLAY_BLEND
targetos: Windows
req.typenames: D3DDDI_MULTIPLANE_OVERLAY_BLEND
---

# _D3DDDI_MULTIPLANE_OVERLAY_BLEND enumeration


## -description


Identifies a blend operation to be performed on an overlay plane.


## -enum-fields




### -field D3DDDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE

The overlay plane should ignore data in the alpha channel and make the blended plane entirely opaque.


### -field D3DDDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND

The overlay plane should use the pre-multiplied alpha channel in this plane to blend it with the plane beneath.

