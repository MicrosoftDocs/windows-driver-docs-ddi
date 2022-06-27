---
UID: NE:d3dkmdt._DXGK_DISPLAY_TECHNOLOGY
title: DXGK_DISPLAY_TECHNOLOGY (d3dkmdt.h)
description: Enum used to specify the display technology being used.
old-location: display\dxgk_display_technology.htm
tech.root: display
ms.date: 05/24/2022
keywords: ["DXGK_DISPLAY_TECHNOLOGY enumeration"]
ms.keywords: "*PDXGK_DISPLAY_TECHNOLOGY, DXGK_DISPLAY_TECHNOLOGY, DXGK_DISPLAY_TECHNOLOGY enumeration [Display Devices], DXGK_DT_INVALID, DXGK_DT_LCD, DXGK_DT_OLED, DXGK_DT_OTHER, PDXGK_DISPLAY_TECHNOLOGY, PDXGK_DISPLAY_TECHNOLOGY enumeration pointer [Display Devices], _DXGK_DISPLAY_TECHNOLOGY, d3dkmdt/DXGK_DISPLAY_TECHNOLOGY, d3dkmdt/DXGK_DT_INVALID, d3dkmdt/DXGK_DT_LCD, d3dkmdt/DXGK_DT_OLED, d3dkmdt/DXGK_DT_OTHER, d3dkmdt/PDXGK_DISPLAY_TECHNOLOGY, display.dxgk_display_technology"
req.header: d3dkmdt.h
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
targetos: Windows
req.typenames: DXGK_DISPLAY_TECHNOLOGY, *PDXGK_DISPLAY_TECHNOLOGY
f1_keywords:
 - _DXGK_DISPLAY_TECHNOLOGY
 - d3dkmdt/_DXGK_DISPLAY_TECHNOLOGY
 - PDXGK_DISPLAY_TECHNOLOGY
 - d3dkmdt/PDXGK_DISPLAY_TECHNOLOGY
 - DXGK_DISPLAY_TECHNOLOGY
 - d3dkmdt/DXGK_DISPLAY_TECHNOLOGY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGK_DISPLAY_TECHNOLOGY
 - PDXGK_DISPLAY_TECHNOLOGY
 - DXGK_DISPLAY_TECHNOLOGY
---

# DXGK_DISPLAY_TECHNOLOGY enumeration

## -description

Enum used to specify the display technology being used.

## -enum-fields

### -field DXGK_DT_INVALID:0

Invalid display technology type.

### -field DXGK_DT_OTHER:1

A display technology which does not match one of the defined, valid types.

### -field DXGK_DT_LCD:2

A display using an LCD panel.

### -field DXGK_DT_OLED:3

A display using an OLED panel.

### -field DXGK_DT_PROJECTOR:4

The display is a projector.

### -field DXGK_DT_MAX:5

Maximum allowed value of this enumeration.
