---
UID: NC:d3dumddi.PFND3DDDI_COMPOSERECTS
title: PFND3DDDI_COMPOSERECTS
author: windows-driver-content
description: The ComposeRects function composes two-dimensional areas from a source surface to a destination surface.
old-location: display\composerects.htm
old-project: display
ms.assetid: b6a6b549-7590-4b27-b759-631fa62a76d2
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.composerects, ComposeRects callback function [Display Devices], ComposeRects, PFND3DDDI_COMPOSERECTS, PFND3DDDI_COMPOSERECTS, d3dumddi/ComposeRects, UserModeDisplayDriver_Functions_fca43b4e-1c5d-46b9-a68f-928378ed22a1.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	ComposeRects
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_COMPOSERECTS callback


## -description


The <b>ComposeRects</b> function composes two-dimensional areas from a source surface to a destination surface. 


## -prototype


````
PFND3DDDI_COMPOSERECTS ComposeRects;

__checkReturn HRESULT APIENTRY ComposeRects(
  _In_       HANDLE                 hDevice,
  _In_ const D3DDDIARG_COMPOSERECTS *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_composerects.md">D3DDDIARG_COMPOSERECTS</a> structure that specifies the parameters that are used to compose rectangular areas.


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

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_composerects.md">ComposeRects</a> could not allocate the required memory for it to complete.

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

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_composerects.md">D3DDDIARG_COMPOSERECTS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_COMPOSERECTS callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

