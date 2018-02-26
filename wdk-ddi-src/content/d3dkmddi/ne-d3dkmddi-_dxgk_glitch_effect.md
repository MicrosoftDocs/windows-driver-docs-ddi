---
UID: NE:d3dkmddi._DXGK_GLITCH_EFFECT
title: "_DXGK_GLITCH_EFFECT"
author: windows-driver-content
description: Enumeration which describes the user visible effect of a glitch during a SetTimingsFromVidPn call.
old-location: display\dxgk_glitch_effect.htm
old-project: display
ms.assetid: EACD5B8D-B579-4EB0-93C7-0B356A67CA8F
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, C, D, DXGK_GLITCH_EFFECT, DXGK_GLITCH_EFFECT enumeration [Display Devices], DXGK_GLITCH_EFFECT_BLACK_CONTENT, DXGK_GLITCH_EFFECT_DEGRADED_CONTENT, DXGK_GLITCH_EFFECT_GARBAGE_CONTENT, DXGK_GLITCH_EFFECT_SEAMLESS, DXGK_GLITCH_EFFECT_STALE_CONTENT, DXGK_GLITCH_EFFECT_SYNC_LOSS, E, F, G, H, I, K, L, T, X, _, _DXGK_GLITCH_EFFECT, d3dkmddi/DXGK_GLITCH_EFFECT, d3dkmddi/DXGK_GLITCH_EFFECT_BLACK_CONTENT, d3dkmddi/DXGK_GLITCH_EFFECT_DEGRADED_CONTENT, d3dkmddi/DXGK_GLITCH_EFFECT_GARBAGE_CONTENT, d3dkmddi/DXGK_GLITCH_EFFECT_SEAMLESS, d3dkmddi/DXGK_GLITCH_EFFECT_STALE_CONTENT, d3dkmddi/DXGK_GLITCH_EFFECT_SYNC_LOSS, display.dxgk_glitch_effect"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_GLITCH_EFFECT
product: Windows
targetos: Windows
req.typenames: DXGK_GLITCH_EFFECT
---

# _DXGK_GLITCH_EFFECT enumeration


## -description


Enumeration which describes the user visible effect of a glitch during a SetTimingsFromVidPn call.




## -syntax


````
typedef enum _DXGK_GLITCH_EFFECT { 
  DXGK_GLITCH_EFFECT_SYNC_LOSS         = 0,
  DXGK_GLITCH_EFFECT_GARBAGE_CONTENT   = 1,
  DXGK_GLITCH_EFFECT_STALE_CONTENT     = 2,
  DXGK_GLITCH_EFFECT_BLACK_CONTENT     = 3,
  DXGK_GLITCH_EFFECT_DEGRADED_CONTENT  = 4,
  DXGK_GLITCH_EFFECT_SEAMLESS          = 255
} DXGK_GLITCH_EFFECT;
````


## -enum-fields




### -field DXGK_GLITCH_EFFECT_SYNC_LOSS

Indicates that the display connected to the target lost sync due to a glitch.  Even a short sync loss will likely lead to the user seeing a black screen while the display device re-syncs.


### -field DXGK_GLITCH_EFFECT_GARBAGE_CONTENT

Indicates that garbage content was sent to the display connected to the target due to a glitch.  Garbage content will be very noticeable to a user.


### -field DXGK_GLITCH_EFFECT_STALE_CONTENT

Indicates that stale content was sent to the display connected to the target due to a glitch.  Display of stale content would cause the affected pixel area to appear frozen.


### -field DXGK_GLITCH_EFFECT_BLACK_CONTENT

Indicates that black content was sent to the display connected to the target due to a glitch.  If the content was black, as would be the case when initializing the display, this will be imperceptible; otherwise it is likely that black content will be noticeable to a user.


### -field DXGK_GLITCH_EFFECT_DEGRADED_CONTENT

Indicates that degraded content was sent to the display connected to the target due to a glitch.  Degraded content would include pixels which are too bright or too dim or which are displayed using a slightly different color space than intended.  Short durations would likely go unnoticed.


### -field DXGK_GLITCH_EFFECT_SEAMLESS

Indicates that there was no user visible glitch.


### -field UINT8



