---
UID: NS:d3dumddi._D3DDDIARG_COMPOSERECTS
title: "_D3DDDIARG_COMPOSERECTS"
author: windows-driver-content
description: The D3DDDIARG_COMPOSERECTS structure describes the parameters that are used to compose rectangular areas.
old-location: display\d3dddiarg_composerects.htm
tech.root: display
ms.assetid: 9360f9c4-e30e-4fc0-ade7-1d98ff8b1d1b
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_COMPOSERECTS, D3DDDIARG_COMPOSERECTS structure [Display Devices], UMDisplayDriver_param_Structs_2f10ffa4-f55f-490b-9aa4-08c0c3e3d924.xml, _D3DDDIARG_COMPOSERECTS, d3dumddi/D3DDDIARG_COMPOSERECTS, display.d3dddiarg_composerects
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_COMPOSERECTS
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_COMPOSERECTS
---

# _D3DDDIARG_COMPOSERECTS structure


## -description


The D3DDDIARG_COMPOSERECTS structure describes the parameters that are used to compose rectangular areas. 


## -struct-fields




### -field hSrcResource

[in] A handle to the source resource that contains the source surface. When the surface is created, the user-mode display driver receives the D3DDDIFMT_A1 (one bit per pixel) value in the <b>Format</b> member and the <b>TextApi</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function. The surface must be created as part of a texture.


### -field SrcSubResourceIndex

[in] The index to the source surface within the source resource. 


### -field hDstResource

[in] A handle to the destination resource that contains the destination surface. When the surface is created, the user-mode display driver receives the D3DDDIFMT_A1 (one bit per pixel) value in the <b>Format</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> in a call to the driver's <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>. The surface must be created as part of a texture. The surface might have been created with the <b>TextApi</b> bit-field flag. 


### -field DstSubResourceIndex

[in] The index to the destination surface within the destination resource. 


### -field hSrcRectDescsVB

[in] A handle to a vertex buffer that contains an array of D3DCOMPOSERECTSRCDESC structures. Each element in the array defines a rectangle on the source surface. When the vertex buffer is created, the user-mode display driver receives the <b>TextApi</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function. 


### -field NumRects

[in] The number of rectangular areas to copy, which is the number of D3DCOMPOSERECTDSTDESC structures in the vertex buffer that is identified by the <b>hDstRectDescsVB</b> member. Drivers should ignore calls to <a href="https://msdn.microsoft.com/b6a6b549-7590-4b27-b759-631fa62a76d2">ComposeRects</a> with <b>NumRects</b> set to greater than 0xFFFF.


### -field hDstRectDescsVB

[in] A handle to a vertex buffer that contains an array of D3DCOMPOSERECTDSTDESC structures. Each element in the array defines where to copy a source rectangle on the destination surface. For more information, see the following Remarks section. When the vertex buffer is created, the user-mode display driver receives the <b>TextApi</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function. 


### -field Operation

[in] A D3DDDI_COMPOSERECTSOP value that describes how to compose the rectangular areas. This member can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DDDICOMPOSERECTS_COPY

</td>
<td>
Copy each source bit to the destination.

</td>
</tr>
<tr>
<td>
D3DDDICOMPOSERECTS_OR

</td>
<td>
Combine source and destination bits in an OR operation and copy to the destination. 

</td>
</tr>
<tr>
<td>
D3DDDICOMPOSERECTS_AND

</td>
<td>
Combine source and destination bits in an AND operation and copy to the destination. 

</td>
</tr>
<tr>
<td>
D3DDDICOMPOSERECTS_NEG

</td>
<td>
Combine the negative of the source bits with the destination bits and copy to the destination. [Dest bit &amp; (~ Src bit)]

</td>
</tr>
</table>
 


### -field XOffset

[in] An offset to add to the <i>x</i>-coordinates of all of the destination rectangular areas. The offset can be negative, which might cause the resultant rectangles to be rejected or clipped. 


### -field YOffset

[in] An offset to add to the <i>y</i>-coordinates of all of the destination rectangular areas. The offset can be negative, which might cause the resultant rectangles to be rejected or clipped. 


## -remarks



The vertex buffers that contain the composing instructions are created with D3DUSAGE_TEXTAPI usage. The following code defines the structures that are contained in the vertex buffer arrays. For more information about these structures, see the DirectX SDK documentation.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>struct D3DCOMPOSERECTSRCDESC {
USHORT X, Y;          // Coordinates of top-left corner
USHORT width, height; // Width and height of the glyph in bits
};</pre>
</td>
</tr>
</table></span></div>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>struct D3DCOMPOSERECTDSTDESC {
USHORT RectDescIndex; // Index of one of the D3DCOMPOSERECTSRCDESC structures in the vertex buffer represented by hSrcRectDescsVB
USHORT reserved;      // Use to align the struct and fields to good boundaries
SHORT X, Y;            // Position in bits in the destination surface
};</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b6a6b549-7590-4b27-b759-631fa62a76d2">ComposeRects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
 

 

