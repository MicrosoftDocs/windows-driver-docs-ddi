---
UID: NS:d3dkmddi._DXGK_GDIARG_STRETCHBLT
title: _DXGK_GDIARG_STRETCHBLT (d3dkmddi.h)
description: The DXGK_GDIARG_STRETCHBLT structure describes the characteristics of a GDI hardware-accelerated stretch bit-block transfer (bitblt) operation.
old-location: display\dxgk_gdiarg_stretchblt.htm
ms.assetid: 11988e4c-9f4b-44cc-bc09-ff6da62f3904
ms.date: 05/10/2018
ms.keywords: BLACKONWHITE, DXGK_GDIARG_STRETCHBLT, DXGK_GDIARG_STRETCHBLT structure [Display Devices], DmStructs_9c8014aa-fdad-474d-a1a1-182020850e17.xml, WHITEONBLACK, _DXGK_GDIARG_STRETCHBLT, d3dkmddi/DXGK_GDIARG_STRETCHBLT, display.dxgk_gdiarg_stretchblt
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_GDIARG_STRETCHBLT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_GDIARG_STRETCHBLT
---

# _DXGK_GDIARG_STRETCHBLT structure


## -description


The DXGK_GDIARG_STRETCHBLT structure describes the characteristics of a GDI hardware-accelerated stretch <a href="https://msdn.microsoft.com/bf5fa319-14ec-40df-be7a-89c07ce519ad">bit-block transfer (bitblt)</a> operation.


## -struct-fields




### -field SrcRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that defines the rectangular area to be copied. This rectangle is specified in the coordinate system of the source surface and is defined by two points: upper left and lower right. The two points that define the rectangle are always well ordered. 

The source rectangle will never exceed the bounds of the source surface, so it will never overhang the source surface. 

This rectangle is mapped to the destination rectangle defined by <b>DstRect</b>. 

For more information, see the Remarks section.


### -field DstRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that defines the rectangular area to be modified. This rectangle is specified in the coordinate system of the destination surface and is defined by two points: upper left and lower right. The rectangle is lower-right exclusive; that is, its lower and right edges are not a part of the bit-block transfer. The two points that define the rectangle are always well ordered. 

The destination rectangle defined by <b>DstRect</b> can exceed the bounds of the destination surface, but sub-rectangles cannot. Additionally, all sub-rectangles are guaranteed to fit inside the destination surface. Sub-rectangles can be constrained further by a bounding rectangle that is smaller than the destination rectangle. 

For more information, see the Remarks section.


### -field DstAllocationIndex

[in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>DstRect</b> destination rectangle.
     


### -field SrcAllocationIndex

[in] An index of the element in the allocation list that specifies the allocation that is referenced by the SrcRect source rectangle.
     


### -field NumSubRects

The number of sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.



### -field pSubRects

[in] A pointer to the sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.


### -field Mode


[in] Specifies how source pixels are combined to produce output pixels based on whether the following values that are defined in <i>Wingdi.h</i> are set:
		  
        
       

|Value|Meaning|
|--- |--- |
|BLACKONWHITE|On a shrinking bit-block transfer, pixels should be combined with a Boolean AND operation. On a stretching bit-block transfer, pixels should be replicated.|
|WHITEONBLACK|On a shrinking bit-block transfer, pixels should be combined with a Boolean OR operation. On a stretching bit-block transfer, pixels should be replicated.|
 
This type of operation will be processed only if the driver has set the <b>SupportMonoStretchBltModes</b> member in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562004">DXGK_PRESENTATIONCAPS</a> structure.


### -field MirrorX

[in] Specifies whether the stretch bit-block transfer will be performed in mirror mode in the xdirection. This type of operation will be processed only if the value of <b>MirrorX</b> is nonzero and the driver has set the <b>SupportMirrorStretchBlt</b> member in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562004">DXGK_PRESENTATIONCAPS</a> structure.
       


### -field MirrorY

[in] Specifies whether the stretch bit-block transfer will be performed in mirror mode in the y direction. This type of operation will be processed only if the value of <b>MirrorY</b> is nonzero and the driver has set the <b>SupportMirrorStretchBlt</b> member in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562004">DXGK_PRESENTATIONCAPS</a> structure.
       


### -field Flags

[in] Optional UINT value that can be used to debug driver code.
      


### -field SrcPitch

[in] The pitch of the source surface, in bytes.
     


## -remarks



The x and y stretch ratios are computed respectively as the ratios of the x and y sizes of the <b>DstRect</b> and <b>SrcRect</b> members.

The HALFTONE mode and STRETCH_HALFTONE modes that are defined in <i>Wingdi.h</i> will never be set in the <b>Mode</b> member. The COLORONCOLOR mode can be set in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561074">DXGK_GDIARG_ALPHABLEND</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561091">DXGK_GDIARG_TRANSPARENTBLT</a> structures.

When sub-rectangles are transformed to the source surface space, the result is guaranteed to be within the source surface. The transformation of a sub-rectangle's coordinates in the destination surface to coordinates  in the source surface is defined by the following formulas, where

<ul>
<li>(Xd, Yd) is a point inside the sub-rectangle</li>
<li>(Xs, Ys) is a point inside the source rectangle</li>
</ul>

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561074">DXGK_GDIARG_ALPHABLEND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561091">DXGK_GDIARG_TRANSPARENTBLT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562004">DXGK_PRESENTATIONCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
 

 

