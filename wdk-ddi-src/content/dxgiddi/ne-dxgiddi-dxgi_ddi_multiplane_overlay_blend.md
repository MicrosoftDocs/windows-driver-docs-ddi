---
UID: NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
title: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND (dxgiddi.h)
description: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND enumeration identifies a blend operation to be performed on an overlay plane.
old-location: display\dxgi_ddi_multiplane_overlay_blend.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGI_DDI_MULTIPLANE_OVERLAY_BLEND enumeration"]
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND, DXGI_DDI_MULTIPLANE_OVERLAY_BLEND enumeration [Display Devices], DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND, DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE, display.dxgi_ddi_multiplane_overlay_blend, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_BLEND, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE
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
targetos: Windows
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
f1_keywords:
 - DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
 - dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dxgiddi.h
api_name:
 - DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
---

# DXGI_DDI_MULTIPLANE_OVERLAY_BLEND enumeration


## -description

Identifies a blend operation to be performed on an overlay plane.

## -enum-fields

### -field DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE

The overlay plane should ignore data in the alpha channel and make the blended plane entirely opaque.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND

The overlay plane should use the pre-multiplied alpha channel in this plane to blend it with the plane beneath.

