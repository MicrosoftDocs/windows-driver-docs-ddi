---
UID: NS:d3dkmddi._DXGK_GDIARG_STRETCHBLT
title: DXGK_GDIARG_STRETCHBLT (d3dkmddi.h)
description: Learn more about the DXGK_GDIARG_STRETCHBLT structure.
ms.date: 06/09/2023
keywords: ["DXGK_GDIARG_STRETCHBLT structure"]
ms.keywords: BLACKONWHITE, DXGK_GDIARG_STRETCHBLT, DXGK_GDIARG_STRETCHBLT structure [Display Devices], DmStructs_9c8014aa-fdad-474d-a1a1-182020850e17.xml, WHITEONBLACK, _DXGK_GDIARG_STRETCHBLT, d3dkmddi/DXGK_GDIARG_STRETCHBLT, display.dxgk_gdiarg_stretchblt
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
req.typenames: DXGK_GDIARG_STRETCHBLT
f1_keywords:
 - _DXGK_GDIARG_STRETCHBLT
 - d3dkmddi/_DXGK_GDIARG_STRETCHBLT
 - DXGK_GDIARG_STRETCHBLT
 - d3dkmddi/DXGK_GDIARG_STRETCHBLT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_GDIARG_STRETCHBLT
 - DXGK_GDIARG_STRETCHBLT
---

# DXGK_GDIARG_STRETCHBLT structure

## -description

The **DXGK_GDIARG_STRETCHBLT** structure describes the characteristics of a GDI hardware-accelerated stretch bit-block transfer (bitblt) operation.

## -struct-fields

### -field SrcRect [in]

A [**RECT**](/windows/win32/api/windef/ns-windef-rect) structure that defines the rectangular area to be copied. This rectangle is specified in the coordinate system of the source surface and is defined by two points: upper left and lower right. The two points that define the rectangle are always well ordered.

The source rectangle will never exceed the bounds of the source surface, so it will never overhang the source surface.

This rectangle is mapped to the destination rectangle defined by **DstRect**.

For more information, see the Remarks section.

### -field DstRect [in]

A [**RECT**](/windows/win32/api/windef/ns-windef-rect) structure that defines the rectangular area to be modified. This rectangle is specified in the coordinate system of the destination surface and is defined by two points: upper left and lower right. The rectangle is lower-right exclusive; that is, its lower and right edges are not a part of the bit-block transfer. The two points that define the rectangle are always well ordered.

The destination rectangle defined by **DstRect** can exceed the bounds of the destination surface, but sub-rectangles cannot. Additionally, all sub-rectangles are guaranteed to fit inside the destination surface. Sub-rectangles can be constrained further by a bounding rectangle that is smaller than the destination rectangle.

For more information, see the Remarks section.

### -field DstAllocationIndex [in]

An index of the element in the allocation list that specifies the allocation that is referenced by the **DstRect** destination rectangle.

### -field SrcAllocationIndex [in]

An index of the element in the allocation list that specifies the allocation that is referenced by the SrcRect source rectangle.

### -field NumSubRects

The number of sub-rectangles in the destination surface space that is bounded by the **DstRect** destination rectangle.

### -field pSubRects [in]

A pointer to the sub-rectangles in the destination surface space that is bounded by the **DstRect** destination rectangle.

### -field Mode [in]

Specifies how source pixels are combined to produce output pixels based on whether the following values that are defined in *Wingdi.h* are set:

|Value|Meaning|
|--- |--- |
|BLACKONWHITE|On a shrinking bit-block transfer, pixels should be combined with a Boolean AND operation. On a stretching bit-block transfer, pixels should be replicated.|
|WHITEONBLACK|On a shrinking bit-block transfer, pixels should be combined with a Boolean OR operation. On a stretching bit-block transfer, pixels should be replicated.|

This type of operation will be processed only if the driver has set the **SupportMonoStretchBltModes** member in the [**DXGK_PRESENTATIONCAPS**](ns-d3dkmddi-_dxgk_presentationcaps.md) structure.

### -field MirrorX [in]

Specifies whether the stretch bit-block transfer will be performed in mirror mode in the xdirection. This type of operation will be processed only if the value of **MirrorX** is nonzero and the driver has set the **SupportMirrorStretchBlt** member in the [**DXGK_PRESENTATIONCAPS**](ns-d3dkmddi-_dxgk_presentationcaps.md) structure.

### -field MirrorY [in]

Specifies whether the stretch bit-block transfer will be performed in mirror mode in the y direction. This type of operation will be processed only if the value of **MirrorY** is nonzero and the driver has set the **SupportMirrorStretchBlt** member in the [**DXGK_PRESENTATIONCAPS**](ns-d3dkmddi-_dxgk_presentationcaps.md) structure.

### -field Flags [in]

Optional UINT value that can be used to debug driver code.

### -field SrcPitch [in]

The pitch of the source surface, in bytes.

## -remarks

The x and y stretch ratios are computed respectively as the ratios of the x and y sizes of the **DstRect** and **SrcRect** members.

The HALFTONE mode and STRETCH_HALFTONE modes that are defined in *Wingdi.h* will never be set in the **Mode** member. The COLORONCOLOR mode can be set in the [**DXGK_GDIARG_ALPHABLEND**](ns-d3dkmddi-_dxgk_gdiarg_alphablend.md) and [**DXGK_GDIARG_TRANSPARENTBLT**](ns-d3dkmddi-_dxgk_gdiarg_transparentblt.md) structures.

When sub-rectangles are transformed to the source surface space, the result is guaranteed to be within the source surface. The transformation of a sub-rectangle's coordinates in the destination surface to coordinates  in the source surface is defined by the following formulas, where

* (Xd, Yd) is a point inside the sub-rectangle
* (Xs, Ys) is a point inside the source rectangle

```cpp
float Ws = SrcRect.right - SrcRect.left;
float Wd = DstRect.right - DstRect.left;
int Xs = round((Xd - DstRect.left + 0.5) * Ws/Wd + SrcRect.left - 0.5)
OR
int Xs = truncate((Xd - DstRect.left + 0.5) * Ws/Wd + SrcRect.left)

float Hs = SrcRect.bottom - SrcRect.top;
float Hd = DstRect.bottom - DstRect.top;
int Ys = round((Yd - DstRect.top + 0.5) * Hs/Hd + SrcRect.top - 0.5)
OR
int Ys = truncate((Yd - DstRect.top + 0.5) * Hs/Hd + SrcRect.top)
```

## -see-also

 [**DXGK_GDIARG_ALPHABLEND**](ns-d3dkmddi-_dxgk_gdiarg_alphablend.md)

[**DXGK_GDIARG_TRANSPARENTBLT**](ns-d3dkmddi-_dxgk_gdiarg_transparentblt.md)

[**DXGK_PRESENTATIONCAPS**](ns-d3dkmddi-_dxgk_presentationcaps.md)

[**RECT**](/windows/win32/api/windef/ns-windef-rect)
