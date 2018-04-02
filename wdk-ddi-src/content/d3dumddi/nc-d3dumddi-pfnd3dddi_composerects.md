---
UID: NC:d3dumddi.PFND3DDDI_COMPOSERECTS
title: PFND3DDDI_COMPOSERECTS
author: windows-driver-content
description: The ComposeRects function composes two-dimensional areas from a source surface to a destination surface.
old-location: display\composerects.htm
old-project: display
ms.assetid: b6a6b549-7590-4b27-b759-631fa62a76d2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ComposeRects, ComposeRects callback function [Display Devices], PFND3DDDI_COMPOSERECTS, UserModeDisplayDriver_Functions_fca43b4e-1c5d-46b9-a68f-928378ed22a1.xml, d3dumddi/ComposeRects, display.composerects
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	ComposeRects
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_COMPOSERECTS callback


## -description


The <b>ComposeRects</b> function composes two-dimensional areas from a source surface to a destination surface. 


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542912">D3DDDIARG_COMPOSERECTS</a> structure that specifies the parameters that are used to compose rectangular areas.


## -returns



<b>ComposeRects</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The rectangular areas were successfully composed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/b6a6b549-7590-4b27-b759-631fa62a76d2">ComposeRects</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



The following constraints and validations apply to the <b>ComposeRects</b> function:

<ul>
<li>
The driver should ignore the source rectangular areas that are not completely inside the source surface. 

</li>
<li>
The destination rectangular areas--after applying offsets--can be partially or completely outside the destination surface. The destination rectangular areas are clipped if partially outside and rejected or completely clipped if completely outside. 

</li>
<li>
The same surface cannot be specified for the source and the destination. 

</li>
<li>
Surfaces and vertex buffers that are used with <b>ComposeRects</b> should not be locked. 

</li>
<li>
The source and destination surfaces are formatted as one bit per pixel (D3DDDIFMT_A1) when they are created.

</li>
<li>
In the debug build, the Microsoft Direct3D runtime validates that a source rectangular area description exists for each index in the destination rectangular area description. In the retail build, <b>ComposeRects</b> returns an error if an invalid index exists. 

</li>
<li>
The number of rectangular areas should be less than 0xFFFF to prevent internal overflow during math operations.

</li>
<li>
Surfaces and vertex buffers should be created by using the same display device (graphics context). 

</li>
<li>
Local display memory should be specified for the destination surface.

</li>
</ul>
The following example code shows an operation that <b>ComposeRects</b> performs:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>for (UINT i=0; i &lt; COMPOSERECTS.NumDstRects; i++) {
   if (i &gt;= Size(VertexBuffer(hDstRectDescsVB)) / sizeof(D3DCOMPOSERECTDSTDESC))
      Ignore the rectangle;
   if (VertexBuffer(hDstRectDescsVB)[i].RectDescIndex &gt;= Size(VertexBuffer(hSrcRectDescsVB)) / sizeof(D3DCOMPOSERECTSRCDESC))
      Ignore the rectangle;
   SourceRectangle = VertexBuffer(hSrcResource)[VertexBuffer(hDstRectDescsVB)[i].RectDescIndex];
   DestinationRectangle.X = {VertexBuffer(hDstRectDescsVB)[i].X + COMPOSERECTS.Xoffset;
   DestinationRectangle.Y = {VertexBuffer(hDstRectDescsVB)[i].Y + COMPOSERECTS.Yoffset;
   DestinationRectangle.Width = SourceRectangle.Width;
   DestinationRectangle.Height = SourceRectangle.Height;
   Perform COMPOSERECTS.Operation for each pixel;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542912">D3DDDIARG_COMPOSERECTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

