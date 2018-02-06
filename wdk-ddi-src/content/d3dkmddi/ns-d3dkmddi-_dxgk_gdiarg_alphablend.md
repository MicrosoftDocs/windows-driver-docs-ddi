---
UID: NS:d3dkmddi._DXGK_GDIARG_ALPHABLEND
title: "_DXGK_GDIARG_ALPHABLEND"
author: windows-driver-content
description: The DXGK_GDIARG_ALPHABLEND structure describes the characteristics of a GDI hardware-accelerated alpha blend operation.
old-location: display\dxgk_gdiarg_alphablend.htm
old-project: display
ms.assetid: 8bb9321c-00a0-4360-9a38-fcef2209028c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGK_GDIARG_ALPHABLEND, DmStructs_8cbd2c26-3cda-445f-807d-e80038ccc8bd.xml, d3dkmddi/DXGK_GDIARG_ALPHABLEND, DXGK_GDIARG_ALPHABLEND, display.dxgk_gdiarg_alphablend, DXGK_GDIARG_ALPHABLEND structure [Display Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_GDIARG_ALPHABLEND
product: Windows
targetos: Windows
req.typenames: DXGK_GDIARG_ALPHABLEND
---

# _DXGK_GDIARG_ALPHABLEND structure


## -description


The DXGK_GDIARG_ALPHABLEND structure describes the characteristics of a GDI hardware-accelerated alpha blend operation.


## -syntax


````
typedef struct _DXGK_GDIARG_ALPHABLEND {
  RECT    SrcRect;
  RECT    DstRect;
  UINT    SrcAllocationIndex;
  UINT    DstAllocationIndex;
  UINT    NumSubRects;
  RECT    *pSubRects;
  BYTE    SourceConstantAlpha;
  BOOLEAN SourceHasAlpha;
  UINT    SrcPitch;
} DXGK_GDIARG_ALPHABLEND;
````


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


### -field SrcAllocationIndex

[in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>SrcRect</b> source rectangle.


### -field DstAllocationIndex

[in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>DstRect</b> destination rectangle.


### -field NumSubRects

[in] The number of sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.


### -field pSubRects

[in] A pointer to the sub-rectangles in the destination surface space.


### -field SourceConstantAlpha

[in] The constant blend factor to apply to the entire source surface. This value is in the range of [0,255], where 0 is completely transparent and 255 is completely opaque.


### -field SourceHasAlpha

[in] Defines whether the surface is assumed to have an alpha channel. If <b>TRUE</b>, the surface is assumed to have an alpha channel; otherwise the value is <b>FALSE</b>.


### -field SrcPitch

[in] The pitch of the source surface, in bytes.


## -remarks


If a stretch bit-block transfer (bitblt) operation is required, the x and y stretch ratios are computed respectively as the ratios of the x and y sizes of the <b>DstRect</b> and <b>SrcRect</b> members, and the stretch operation will proceed as if the COLORONCOLOR value in <i>Wingdi.h</i> is set. On a shrinking bit-block transfer, enough pixels should be ignored so that pixels do not need to be combined. On a stretching bit-block transfer, pixels should be replicated.

When sub-rectangles are transformed to the source surface space, the result is guaranteed to be within the source surface. The transformation of a sub-rectangle's coordinates in the destination surface to coordinates  in the source surface is defined by the following formulas, where
<ul>
<li>(Xd, Yd) is a point inside the sub-rectangle</li>
<li>(Xs, Ys) is a point inside the source rectangle</li>
</ul><pre class="syntax" xml:space="preserve"><code>float Ws = SrcRect.right â€“ SrcRect.left;
float Wd = DstRect.right â€“ DstRect.left;
int Xs = round((Xd â€“ DstRect.left + 0.5) * Ws/Wd + SrcRect.left â€“ 0.5)
OR
int Xs = truncate((Xd â€“ DstRect.left + 0.5) * Ws/Wd + SrcRect.left)

float Hs = SrcRect.bottom â€“ SrcRect.top;
float Hd = DstRect.bottom â€“ DstRect.top;
int Ys = round((Yd â€“ DstRect.top + 0.5) * Hs/Hd + SrcRect.top â€“ 0.5)
OR
int Ys = truncate((Yd â€“ DstRect.top + 0.5) * Hs/Hd + SrcRect.top)</code></pre>


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_GDIARG_ALPHABLEND structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

