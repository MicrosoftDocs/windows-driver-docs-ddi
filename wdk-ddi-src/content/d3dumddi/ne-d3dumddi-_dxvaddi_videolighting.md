---
UID: NE:d3dumddi._DXVADDI_VIDEOLIGHTING
title: _DXVADDI_VIDEOLIGHTING (d3dumddi.h)
description: The DXVADDI_VIDEOLIGHTING enumeration type contains values that identify lighting conditions for viewing video.
old-location: display\dxvaddi_videolighting.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXVADDI_VIDEOLIGHTING enumeration"]
ms.keywords: DXVA2_Structs_63ea0b3a-8eef-4960-b3a5-2587eae26917.xml, DXVADDI_VIDEOLIGHTING, DXVADDI_VIDEOLIGHTING enumeration [Display Devices], DXVADDI_VideoLightingMask, DXVADDI_VideoLighting_Unknown, DXVADDI_VideoLighting_bright, DXVADDI_VideoLighting_dark, DXVADDI_VideoLighting_dim, DXVADDI_VideoLighting_office, _DXVADDI_VIDEOLIGHTING, d3dumddi/DXVADDI_VIDEOLIGHTING, d3dumddi/DXVADDI_VideoLightingMask, d3dumddi/DXVADDI_VideoLighting_Unknown, d3dumddi/DXVADDI_VideoLighting_bright, d3dumddi/DXVADDI_VideoLighting_dark, d3dumddi/DXVADDI_VideoLighting_dim, d3dumddi/DXVADDI_VideoLighting_office, display.dxvaddi_videolighting
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: DXVADDI_VIDEOLIGHTING
f1_keywords:
 - _DXVADDI_VIDEOLIGHTING
 - d3dumddi/_DXVADDI_VIDEOLIGHTING
 - DXVADDI_VIDEOLIGHTING
 - d3dumddi/DXVADDI_VIDEOLIGHTING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVADDI_VIDEOLIGHTING
---

# _DXVADDI_VIDEOLIGHTING enumeration


## -description

The DXVADDI_VIDEOLIGHTING enumeration type contains values that identify lighting conditions for viewing video.

## -enum-fields

### -field DXVADDI_VideoLightingMask

The video lighting mask. The first 4 (0x0F) bits of a DWORD can be used to specify video lighting.

### -field DXVADDI_VideoLighting_Unknown

The video lighting condition is not specified. The default is dim.

### -field DXVADDI_VideoLighting_bright

A bright light for viewing video (for example, outside lighting conditions).

### -field DXVADDI_VideoLighting_office

A medium brightness light for viewing video (for example, lighting conditions in home offices).

### -field DXVADDI_VideoLighting_dim

A dim light for viewing video (for example, low-level lighting in a living room while watching television).

### -field DXVADDI_VideoLighting_dark

Near-darkness for viewing video (for example, movie-theatre lighting).

## -remarks

One of the values of DXVADDI_VIDEOLIGHTING can be specified in the <b>VideoLighting</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a>.

The video lighting values can be used to alter the gamma to generate a comparable experience in a different lighting condition.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a>
