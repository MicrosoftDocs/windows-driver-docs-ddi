---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION
title: _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION (d3dkmddi.h)
description: Specifies information about any additional transforms that should occur after the planes are composed.
old-location: display\dxgk_multiplane_overlay_post_composition.htm

ms.assetid: 71D57E42-C1E7-4A0E-80B3-DD39388552C5
ms.date: 04/16/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION, DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION, display.dxgk_multiplane_overlay_post_composition
ms.topic: struct
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
- DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION
---

# _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION structure


## -description


Specifies information about any additional transforms that should occur after the planes are composed.


## -struct-fields




### -field Flags

A DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_FLAGS structure indicating additional transform information.


### -field SrcRect

Contains the source rect of the virtual mode.


### -field DstRect

Contains the destination rect of the virtual mode.


### -field Rotation

Indicates additional rotation that should occur on the final image.


## -remarks



The source mode contains the virtual mode size and the destination rectangle indicates how the virtual mode maps to the physical mode.

For example, if a 1024x768 virtual mode is used with 1920x1080 physical mode, the following configurations are possible:

Stretch mode:

* SrcRect = {0, 0, 1024, 768}
* DstRect = {0, 0, 1920, 1080}

Centered mode:

* SrcRect = {0, 0, 1024, 768}
* DstRect = {448, 156, 1472, 924}

Aspect ratio stretched:

* SrcRect = {0, 0, 1024, 768}
* DstRect = {240, 0, 1680, 1080}   // 1080p monitor resolution






