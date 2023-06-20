---
UID: NE:d3dkmddi._DXGK_GDIROP_COLORFILL
title: DXGK_GDIROP_COLORFILL (d3dkmddi.h)
description: Learn more about the DXGK_GDIROP_COLORFILL enumeration.
ms.date: 06/09/2023
keywords: ["DXGK_GDIROP_COLORFILL enumeration"]
ms.keywords: DXGK_GDIROPCF_DSTINVERT, DXGK_GDIROPCF_INVALID, DXGK_GDIROPCF_PATAND, DXGK_GDIROPCF_PATCOPY, DXGK_GDIROPCF_PATINVERT, DXGK_GDIROPCF_PATOR, DXGK_GDIROPCF_PDXN, DXGK_GDIROPCF_ROP3, DXGK_GDIROP_COLORFILL, DXGK_GDIROP_COLORFILL enumeration [Display Devices], DmEnums_eaf6bb81-110e-428b-9dc8-22d152bce5b9.xml, _DXGK_GDIROP_COLORFILL, d3dkmddi/DXGK_GDIROPCF_DSTINVERT, d3dkmddi/DXGK_GDIROPCF_INVALID, d3dkmddi/DXGK_GDIROPCF_PATAND, d3dkmddi/DXGK_GDIROPCF_PATCOPY, d3dkmddi/DXGK_GDIROPCF_PATINVERT, d3dkmddi/DXGK_GDIROPCF_PATOR, d3dkmddi/DXGK_GDIROPCF_PDXN, d3dkmddi/DXGK_GDIROPCF_ROP3, d3dkmddi/DXGK_GDIROP_COLORFILL, display.dxgk_gdirop_colorfill
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
req.typenames: DXGK_GDIROP_COLORFILL
f1_keywords:
 - _DXGK_GDIROP_COLORFILL
 - d3dkmddi/_DXGK_GDIROP_COLORFILL
 - DXGK_GDIROP_COLORFILL
 - d3dkmddi/DXGK_GDIROP_COLORFILL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_GDIROP_COLORFILL
 - DXGK_GDIROP_COLORFILL
---

# DXGK_GDIROP_COLORFILL enumeration

## -description

The **DXGK_GDIROP_COLORFILL** enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated color fill operation.

## -enum-fields

### -field DXGK_GDIROPCF_INVALID:0

Indicates that the GDI raster operation is invalid.

### -field DXGK_GDIROPCF_PATCOPY:1

Indicates that the specified color is copied into all pixels of the destination rectangle.

### -field DXGK_GDIROPCF_PATINVERT:2

Indicates that the specified color is combined with the colors of the destination rectangle by using the Boolean XOR operator.

### -field DXGK_GDIROPCF_PDXN:3

Indicates that the specified color is combined with the colors of the destination rectangle by using the Boolean NOT(XOR) operator.

### -field DXGK_GDIROPCF_DSTINVERT:4

Indicates that the destination rectangle is inverted.

### -field DXGK_GDIROPCF_PATAND:5

Indicates that the specified color is combined with the colors of the destination rectangle by using the Boolean AND operator.

### -field DXGK_GDIROPCF_PATOR:6

Indicates that the colors of the specified pattern are combined with the colors of the destination rectangle by using the Boolean OR operator.

### -field DXGK_GDIROPCF_ROP3:7

Indicates that a ternary GDI raster operation (ROP3) will be applied.
