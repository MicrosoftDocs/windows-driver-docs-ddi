---
UID: NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS
title: DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS
author: windows-driver-content
description: Identifies a flip operation to be performed on an overlay plane.
old-location: display\dxgi_ddi_multiplane_overlay_flags.htm
old-project: display
ms.assetid: 74245a8b-1b52-4336-a744-1aedaca0eef5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgi_ddi_multiplane_overlay_flags, DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_HORIZONTAL_FLIP, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_VERTICAL_FLIP, DXGI_MULTIPLANE_OVERLAY_FLAG_FULLSCREEN_POST_COMPOSITION, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS, DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS enumeration [Display Devices], DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS, dxgiddi/DXGI_MULTIPLANE_OVERLAY_FLAG_FULLSCREEN_POST_COMPOSITION, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_HORIZONTAL_FLIP, DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_VERTICAL_FLIP
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
-	DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS
---

# DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS enumeration


## -description


Identifies a flip operation to be performed on an overlay plane.


## -syntax


````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS { 
  DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_VERTICAL_FLIP            = 0x1,
  DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_HORIZONTAL_FLIP          = 0x2,
  DXGI_MULTIPLANE_OVERLAY_FLAG_FULLSCREEN_POST_COMPOSITION  = 0x4
} DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS;
````


## -enum-fields




### -field DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_VERTICAL_FLIP

The overlay plane should flip the data vertically, making it appear upside-down.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_HORIZONTAL_FLIP

The overlay plane should flip the data horizontally, making it appear as a right-to-left mirror image.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_FULLSCREEN_POST_COMPOSITION




#### - DXGI_MULTIPLANE_OVERLAY_FLAG_FULLSCREEN_POST_COMPOSITION

Indicates that the plane is to be stretched using panel fitter hardware.

This should only be set for plane 0.

Composition with other multi-plane overlay planes may be supported, but the ClipRects of those planes must be bound to the SourceRect of this plane.


