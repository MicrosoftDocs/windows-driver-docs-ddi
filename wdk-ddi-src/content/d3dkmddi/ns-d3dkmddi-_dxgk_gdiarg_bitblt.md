---
UID: NS:d3dkmddi._DXGK_GDIARG_BITBLT
title: "_DXGK_GDIARG_BITBLT"
author: windows-driver-content
description: The DXGK_GDIARG_BITBLT structure describes the characteristics of a GDI hardware-accelerated bit-block transfer (bitblt) with no stretching.
old-location: display\dxgk_gdiarg_bitblt.htm
tech.root: display
ms.assetid: 367ee4cb-5074-478d-8836-962f96acf103
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_GDIARG_BITBLT, DXGK_GDIARG_BITBLT structure [Display Devices], DmStructs_717d3dc5-03a2-4814-b351-6ea7fb270f26.xml, _DXGK_GDIARG_BITBLT, d3dkmddi/DXGK_GDIARG_BITBLT, display.dxgk_gdiarg_bitblt
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_GDIARG_BITBLT
product:
- Windows
targetos: Windows
req.typenames: DXGK_GDIARG_BITBLT
---

# _DXGK_GDIARG_BITBLT structure


## -description


The DXGK_GDIARG_BITBLT structure describes the characteristics of a GDI hardware-accelerated <a href="https://msdn.microsoft.com/bf5fa319-14ec-40df-be7a-89c07ce519ad">bit-block transfer (bitblt)</a> with no stretching.


## -struct-fields




### -field SrcRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that defines the rectangular area to be copied. This rectangle is specified in the coordinate system of the source surface and is defined by two points: upper left and lower right. The two points that define the rectangle are always well ordered. 

The source rectangle can exceed the bounds of the source surface.

This rectangle is mapped to the destination rectangle defined by <b>DstRect</b>. <b>SrcRect</b> is used to transform sub-rectangles from the source space to the destination space. 

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


      [in] A pointer to the sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.
     


### -field Rop


      [in] An 8-bit value that specifies a GDI raster operation (ROP) that is defined by the constant values of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561095">DXGK_GDIROP_BITBLT</a> enumeration.
     


### -field Rop3


      [in] An 8-bit value that specifies a ternary GDI raster operation (ROP3) that combines a brush, a source bitmap, and a destination bitmap in one of 256 possible combinations. This type of raster operation will be processed only if the driver has set the <b>SupportAllBltRops</b> member in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562004">DXGK_PRESENTATIONCAPS</a> structure.
     


### -field SrcPitch


      [in] The pitch of the source surface, in bytes. For more information on using pitch, see Remarks section.
     


### -field DstPitch


      [in] The pitch of the destination surface, in bytes. For more information on using pitch, see Remarks section.
     


## -remarks



The <b>SrcPitch</b> and <b>DstPitch</b> pitch values must be used to determine the byte locations of the <b>SrcRect</b> and <b>DstRect</b> rectangles, respectively, for the following allocations of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff546039">D3DKMDT_GDISURFACETYPE</a>:

D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE

D3DKMDT_GDISURFACE_EXISTINGSYSMEM

Pitch should be ignored for other allocation types.

Pitch is guaranteed to be aligned in the bit-block transfer according to the <b>AlignmentShift</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562004">DXGK_PRESENTATIONCAPS</a> structure (that is, <a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>.PresentationCaps.AlignmentShift).

Where a rectangle is defined by two pixels at coordinates (left, top) and (right, bottom), the address of the first pixel is:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>Allocation.BaseAddress + (top * Pitch) + (left * 4)</pre>
</td>
</tr>
</table></span></div>
The address of the rectangle's last pixel is:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>Allocation.BaseAddress + ((bottom - 1) * Pitch) + ((right - 1) * 4)</pre>
</td>
</tr>
</table></span></div>
When sub-rectangles are transformed to the source surface space, the result is guaranteed to be within the source surface. This transformation is defined by the following formula:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>SrcSubRect.left = SubRect.left - DstRect.left + SrcRect.left;
SrcSubRect.right = SubRect.right - DstRect.left + SrcRect.left;
SrcSubRect.top = SubRect.top - DstRect.top + SrcRect.top;
SrcSubRect.bottom = SubRect.bottom - DstRect.top + SrcRect.top;</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546039">D3DKMDT_GDISURFACETYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561095">DXGK_GDIROP_BITBLT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562004">DXGK_PRESENTATIONCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
 

 

