---
UID: NE:d3dkmddi._DXGK_GLITCH_DURATION
title: _DXGK_GLITCH_DURATION (d3dkmddi.h)
description: Enumeration that describes the duration of a user visible effect of a glitch during a SetTimingsFromVidPn call.
old-location: display\dxgk_glitch_duration.htm
ms.assetid: 8B6597A7-D652-4143-9320-7FB8E98FE8EC
ms.date: 05/10/2018
ms.keywords: DXGK_GLITCH_DURATION, DXGK_GLITCH_DURATION enumeration [Display Devices], DXGK_GLITCH_DURATION_INDEFINITE, DXGK_GLITCH_DURATION_MULTI_FRAME, DXGK_GLITCH_DURATION_MULTI_LINE, DXGK_GLITCH_DURATION_NONE, DXGK_GLITCH_DURATION_SINGLE_FRAME, DXGK_GLITCH_DURATION_SINGLE_LINE, _DXGK_GLITCH_DURATION, d3dkmddi/DXGK_GLITCH_DURATION, d3dkmddi/DXGK_GLITCH_DURATION_INDEFINITE, d3dkmddi/DXGK_GLITCH_DURATION_MULTI_FRAME, d3dkmddi/DXGK_GLITCH_DURATION_MULTI_LINE, d3dkmddi/DXGK_GLITCH_DURATION_NONE, d3dkmddi/DXGK_GLITCH_DURATION_SINGLE_FRAME, d3dkmddi/DXGK_GLITCH_DURATION_SINGLE_LINE, display.dxgk_glitch_duration
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_GLITCH_DURATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_GLITCH_DURATION
---

# _DXGK_GLITCH_DURATION enumeration


## -description


Enumeration that describes the duration of a user visible effect of a glitch during a SetTimingsFromVidPn call.


## -enum-fields




### -field DXGK_GLITCH_DURATION_INDEFINITE

Indicates that a glitch is unresolved.


### -field DXGK_GLITCH_DURATION_MULTI_FRAME

Indicates that a glitch lasted for multiple frames.


### -field DXGK_GLITCH_DURATION_SINGLE_FRAME

Indicates that a glitch lasted for no more than one frame.


### -field DXGK_GLITCH_DURATION_MULTI_LINE

Indicates that a glitch lasted for multiple lines within a frame.


### -field DXGK_GLITCH_DURATION_SINGLE_LINE

Indicates that a glitch lasted for no more than one line.


### -field DXGK_GLITCH_DURATION_NONE

Indicates that there was no user visible glitch.


### -field UINT8



