---
UID: NE:d3dkmddi._DXGK_RENDERKM_OPERATION
title: DXGK_RENDERKM_OPERATION (d3dkmddi.h)
description: Learn more about the DXGK_RENDERKM_OPERATION enumeration.
ms.date: 06/09/2023
keywords: ["DXGK_RENDERKM_OPERATION enumeration"]
ms.keywords: DXGK_GDIOP_ALPHABLEND, DXGK_GDIOP_BITBLT, DXGK_GDIOP_CLEARTYPEBLEND, DXGK_GDIOP_COLORFILL, DXGK_GDIOP_ESCAPE, DXGK_GDIOP_STRETCHBLT, DXGK_GDIOP_TRANSPARENTBLT, DXGK_RENDERKM_OPERATION, DXGK_RENDERKM_OPERATION enumeration [Display Devices], DmEnums_f7b836bc-00ed-4ecc-8bb7-460e3e44d165.xml, _DXGK_RENDERKM_OPERATION, d3dkmddi/DXGK_GDIOP_ALPHABLEND, d3dkmddi/DXGK_GDIOP_BITBLT, d3dkmddi/DXGK_GDIOP_CLEARTYPEBLEND, d3dkmddi/DXGK_GDIOP_COLORFILL, d3dkmddi/DXGK_GDIOP_ESCAPE, d3dkmddi/DXGK_GDIOP_STRETCHBLT, d3dkmddi/DXGK_GDIOP_TRANSPARENTBLT, d3dkmddi/DXGK_RENDERKM_OPERATION, display.dxgk_renderkm_operation
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
tech.root: display
req.typenames: DXGK_RENDERKM_OPERATION
f1_keywords:
 - _DXGK_RENDERKM_OPERATION
 - d3dkmddi/_DXGK_RENDERKM_OPERATION
 - DXGK_RENDERKM_OPERATION
 - d3dkmddi/DXGK_RENDERKM_OPERATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_RENDERKM_OPERATION
 - DXGK_RENDERKM_OPERATION
---

# DXGK_RENDERKM_OPERATION enumeration

## -description

The **DXGK_RENDERKM_OPERATION** enumeration indicates the type of GDI hardware-accelerated rendering operation to perform when the [**DxgkDdiRenderKm**](nc-d3dkmddi-dxgkddi_renderkm.md) function is called.

## -enum-fields

### -field DXGK_GDIOP_BITBLT:1

Indicates a bit-block transfer (bitblt).

### -field DXGK_GDIOP_COLORFILL:2

Indicates a color fill.

### -field DXGK_GDIOP_ALPHABLEND:3

Indicates an alpha blend.

### -field DXGK_GDIOP_STRETCHBLT:4

Indicates a stretch blt.

### -field DXGK_GDIOP_ESCAPE:5

Reserved for future use. The driver should skip this command when setting the value of the <b>CommandSize</b> member of the [**DXGK_RENDERKM_COMMAND**](ns-d3dkmddi-_dxgk_renderkm_command.md) structure.

### -field DXGK_GDIOP_TRANSPARENTBLT:6

Indicates a blt with transparency.

### -field DXGK_GDIOP_CLEARTYPEBLEND:7

Indicates a ClearType blend.

## -see-also

[**DXGK_RENDERKM_COMMAND**](ns-d3dkmddi-_dxgk_renderkm_command.md)

[**DxgkDdiRenderKm**](nc-d3dkmddi-dxgkddi_renderkm.md)
