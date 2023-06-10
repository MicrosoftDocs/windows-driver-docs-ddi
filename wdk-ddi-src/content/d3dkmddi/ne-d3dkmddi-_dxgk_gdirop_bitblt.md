---
UID: NE:d3dkmddi._DXGK_GDIROP_BITBLT
title: DXGK_GDIROP_BITBLT (d3dkmddi.h)
description: Learn more about the DXGK_GDIROP_COLORFILL enumeration.
ms.date: 06/09/2023
keywords: ["DXGK_GDIROP_BITBLT enumeration"]
ms.keywords: DXGK_GDIROP_BITBLT, DXGK_GDIROP_BITBLT enumeration [Display Devices], DXGK_GDIROP_INVALID, DXGK_GDIROP_ROP3, DXGK_GDIROP_SRCAND, DXGK_GDIROP_SRCCOPY, DXGK_GDIROP_SRCINVERT, DXGK_GDIROP_SRCOR, DmEnums_ac0fe82c-71cb-4756-a580-37d138873b2d.xml, _DXGK_GDIROP_BITBLT, d3dkmddi/DXGK_GDIROP_BITBLT, d3dkmddi/DXGK_GDIROP_INVALID, d3dkmddi/DXGK_GDIROP_ROP3, d3dkmddi/DXGK_GDIROP_SRCAND, d3dkmddi/DXGK_GDIROP_SRCCOPY, d3dkmddi/DXGK_GDIROP_SRCINVERT, d3dkmddi/DXGK_GDIROP_SRCOR, display.dxgk_gdirop_bitblt
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
req.typenames: DXGK_GDIROP_BITBLT
f1_keywords:
 - _DXGK_GDIROP_BITBLT
 - d3dkmddi/_DXGK_GDIROP_BITBLT
 - DXGK_GDIROP_BITBLT
 - d3dkmddi/DXGK_GDIROP_BITBLT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_GDIROP_BITBLT
 - DXGK_GDIROP_BITBLT
---

# DXGK_GDIROP_BITBLT enumeration

## -description

The **DXGK_GDIROP_COLORFILL** enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated bit-block transfer (bitblt) operation.

## -enum-fields

### -field DXGK_GDIROP_INVALID:0

Indicates that the GDI raster operation is invalid.

### -field DXGK_GDIROP_SRCCOPY:1

Indicates that the source rectangle is copied to the destination rectangle.

### -field DXGK_GDIROP_SRCINVERT:2

Indicates that the color of each pixel of the source rectangle is combined with the color of the respective pixel of the destination rectangle by using the Boolean XOR operator.

### -field DXGK_GDIROP_SRCAND:3

Indicates that the color of each pixel of the source rectangle is combined with the color of the respective pixel of the destination rectangle by using the Boolean AND operator.

### -field DXGK_GDIROP_SRCOR:4

Indicates that the color of each pixel of the source rectangle is combined with the color of the respective pixel of the destination rectangle by using the Boolean OR operator.

### -field DXGK_GDIROP_ROP3:5

Indicates that a ternary GDI raster operation (ROP3) will be applied.

## -see-also

[**DXGK_GDIARG_BITBLT**](ns-d3dkmddi-_dxgk_gdiarg_bitblt.md)
