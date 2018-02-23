---
UID: NE:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
title: "_DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE"
author: windows-driver-content
description: Identifies the overlay plane's stereo flip mode. Only the DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE value is supported.
old-location: display\dxgk_multiplane_overlay_stereo_flip_mode.htm
old-project: display
ms.assetid: f226f276-c5d3-460d-9f52-c66ccfd3393f
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE, _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE, DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1, DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0, display.dxgk_multiplane_overlay_stereo_flip_mode, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1, DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0, DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE enumeration [Display Devices], d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE, DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE
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
-	DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
---

# _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE enumeration


## -description


Identifies the overlay plane's stereo flip mode. Only the <b>DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE</b> value is supported.



## -syntax


````
typedef enum _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE { 
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE    = 0,
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0  = 1,
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1  = 2
} DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE;
````


## -enum-fields




### -field DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE

The overplay plane data is not presented in stereo mode.


### -field DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0

Reserved for system use. Do not use in your driver.


### -field DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1

Reserved for system use. Do not use in your driver.

