---
UID: NE:d3dumddi._DXVAHDDDI_ALPHA_FILL_MODE
title: _DXVAHDDDI_ALPHA_FILL_MODE (d3dumddi.h)
description: The DXVAHDDDI_ALPHA_FILL_MODE enumeration contains values that identify the type of alpha fill mode to set.
old-location: display\dxvahdddi_alpha_fill_mode.htm
tech.root: display
ms.assetid: 6b0fdae8-d313-4281-bab0-b3dcc38b19e5
ms.date: 05/10/2018
keywords: ["DXVAHDDDI_ALPHA_FILL_MODE enumeration"]
ms.keywords: DXVA2_Structs_bc53b063-f00e-4589-8bf7-d397925dda55.xml, DXVAHDDDI_ALPHA_FILL_MODE, DXVAHDDDI_ALPHA_FILL_MODE enumeration [Display Devices], DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND, DXVAHDDDI_ALPHA_FILL_MODE_DESTINATION, DXVAHDDDI_ALPHA_FILL_MODE_OPAQUE, DXVAHDDDI_ALPHA_FILL_MODE_SOURCE_STREAM, _DXVAHDDDI_ALPHA_FILL_MODE, d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE, d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND, d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE_DESTINATION, d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE_OPAQUE, d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE_SOURCE_STREAM, display.dxvahdddi_alpha_fill_mode
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_ALPHA_FILL_MODE is supported beginning with the Windows 7 operating system.
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
req.typenames: DXVAHDDDI_ALPHA_FILL_MODE
f1_keywords:
 - _DXVAHDDDI_ALPHA_FILL_MODE
 - d3dumddi/_DXVAHDDDI_ALPHA_FILL_MODE
 - DXVAHDDDI_ALPHA_FILL_MODE
 - d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVAHDDDI_ALPHA_FILL_MODE
---

# _DXVAHDDDI_ALPHA_FILL_MODE enumeration


## -description

The DXVAHDDDI_ALPHA_FILL_MODE enumeration contains values that identify the type of alpha fill mode to set.

## -enum-fields

### -field DXVAHDDDI_ALPHA_FILL_MODE_OPAQUE

A value that specifies to fill the output with opaque alpha channel data.

### -field DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND

A value that specifies to fill the output with the alpha channel data of the background. For more information about background color, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_background_color_data">DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA</a>.

### -field DXVAHDDDI_ALPHA_FILL_MODE_DESTINATION

A value that specifies to keep the alpha channel data unchanged on the target output.

### -field DXVAHDDDI_ALPHA_FILL_MODE_SOURCE_STREAM

A value that specifies to fill the output with the alpha channel data of the destination rectangle in which the source rectangle of the specified input stream is scaled. For more information about the conditions for this value, see the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_alpha_fill_data">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_alpha_fill_data">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_background_color_data">DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA</a>

