---
UID: NE:d3dkmddi._DXGK_GDIROP_COLORFILL
title: _DXGK_GDIROP_COLORFILL (d3dkmddi.h)
description: The DXGK_GDIROP_COLORFILL enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated color fill operation.
old-location: display\dxgk_gdirop_colorfill.htm
ms.date: 05/10/2018
keywords: ["DXGK_GDIROP_COLORFILL enumeration"]
ms.keywords: DXGK_GDIROPCF_DSTINVERT, DXGK_GDIROPCF_INVALID, DXGK_GDIROPCF_PATAND, DXGK_GDIROPCF_PATCOPY, DXGK_GDIROPCF_PATINVERT, DXGK_GDIROPCF_PATOR, DXGK_GDIROPCF_PDXN, DXGK_GDIROPCF_ROP3, DXGK_GDIROP_COLORFILL, DXGK_GDIROP_COLORFILL enumeration [Display Devices], DmEnums_eaf6bb81-110e-428b-9dc8-22d152bce5b9.xml, _DXGK_GDIROP_COLORFILL, d3dkmddi/DXGK_GDIROPCF_DSTINVERT, d3dkmddi/DXGK_GDIROPCF_INVALID, d3dkmddi/DXGK_GDIROPCF_PATAND, d3dkmddi/DXGK_GDIROPCF_PATCOPY, d3dkmddi/DXGK_GDIROPCF_PATINVERT, d3dkmddi/DXGK_GDIROPCF_PATOR, d3dkmddi/DXGK_GDIROPCF_PDXN, d3dkmddi/DXGK_GDIROPCF_ROP3, d3dkmddi/DXGK_GDIROP_COLORFILL, display.dxgk_gdirop_colorfill
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
 - DXGK_GDIROP_COLORFILL
---

# _DXGK_GDIROP_COLORFILL enumeration


## -description

The DXGK_GDIROP_COLORFILL enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated color fill operation.

## -enum-fields

### -field DXGK_GDIROPCF_INVALID

Indicates that the GDI raster operation is invalid.

### -field DXGK_GDIROPCF_PATCOPY

Indicates that the specified color is copied into all pixels of the destination rectangle.

### -field DXGK_GDIROPCF_PATINVERT

Indicates that the specified color is combined with the colors of the destination rectangle by using the Boolean <b>XOR</b> operator.

### -field DXGK_GDIROPCF_PDXN

Indicates that the specified color is combined with the colors of the destination rectangle by using the Boolean <b>NOT(XOR)</b> operator.

### -field DXGK_GDIROPCF_DSTINVERT

Indicates that the destination rectangle is inverted.

### -field DXGK_GDIROPCF_PATAND

Indicates that the specified color is combined with the colors of the destination rectangle by using the Boolean <b>AND</b> operator.

### -field DXGK_GDIROPCF_PATOR

Indicates that the colors of the specified pattern are combined with the colors of the destination rectangle by using the Boolean <b>OR</b> operator.

### -field DXGK_GDIROPCF_ROP3

Indicates that a ternary GDI raster operation (ROP3) will be applied.

