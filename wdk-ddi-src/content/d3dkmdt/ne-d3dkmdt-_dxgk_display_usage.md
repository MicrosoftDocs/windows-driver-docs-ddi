---
UID: NE:d3dkmdt._DXGK_DISPLAY_USAGE
title: DXGK_DISPLAY_USAGE (d3dkmdt.h)
description: Enum used to specify the display type being used.
old-location: display\dxgk_display_usage.htm
tech.root: display
ms.date: 05/24/2022
keywords: ["DXGK_DISPLAY_USAGE enumeration"]
ms.keywords: "*PDXGK_DISPLAY_USAGE, DXGK_DISPLAY_USAGE, DXGK_DISPLAY_USAGE enumeration [Display Devices], DXGK_DU_AR, DXGK_DU_GENERIC, DXGK_DU_INVALID, DXGK_DU_VR, PDXGK_DISPLAY_USAGE, PDXGK_DISPLAY_USAGE enumeration pointer [Display Devices], _DXGK_DISPLAY_USAGE, d3dkmdt/DXGK_DISPLAY_USAGE, d3dkmdt/DXGK_DU_AR, d3dkmdt/DXGK_DU_GENERIC, d3dkmdt/DXGK_DU_INVALID, d3dkmdt/DXGK_DU_VR, d3dkmdt/PDXGK_DISPLAY_USAGE, display.dxgk_display_usage"
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: DXGK_DISPLAY_USAGE, *PDXGK_DISPLAY_USAGE
f1_keywords:
 - _DXGK_DISPLAY_USAGE
 - d3dkmdt/_DXGK_DISPLAY_USAGE
 - PDXGK_DISPLAY_USAGE
 - d3dkmdt/PDXGK_DISPLAY_USAGE
 - DXGK_DISPLAY_USAGE
 - d3dkmdt/DXGK_DISPLAY_USAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGK_DISPLAY_USAGE
 - PDXGK_DISPLAY_USAGE
 - DXGK_DISPLAY_USAGE
---

# DXGK_DISPLAY_USAGE enumeration

## -description

Enum used to specify the manufacturer's intended usage of the display.

## -enum-fields

### -field DXGK_DU_INVALID:0

Invalid usage.

### -field DXGK_DU_GENERIC:1

Generic display type.

### -field DXGK_DU_AR:2

A head mounted augmented reality display.

### -field DXGK_DU_VR:3

A head mounted virtual reality display.

### -field DXGK_DU_MEDICAL_IMAGING:4

Medical imaging.

### -field DXGK_DU_ACCESSORY:5

Accessory.

### -field DXGK_DU_MAX

Maximum value allowed for this enumeration.
