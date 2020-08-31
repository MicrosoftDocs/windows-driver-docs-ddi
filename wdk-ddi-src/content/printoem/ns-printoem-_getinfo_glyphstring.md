---
UID: NS:printoem._GETINFO_GLYPHSTRING
title: _GETINFO_GLYPHSTRING (printoem.h)
description: The GETINFO_GLYPHSTRING structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_glyphstring.htm
tech.root: print
ms.assetid: ebcc1ada-af6f-46c3-a025-97079eb08816
ms.date: 04/20/2018
keywords: ["GETINFO_GLYPHSTRING structure"]
ms.keywords: "*PGETINFO_GLYPHSTRING, GETINFO_GLYPHSTRING, GETINFO_GLYPHSTRING structure [Print Devices], PGETINFO_GLYPHSTRING, PGETINFO_GLYPHSTRING structure pointer [Print Devices], _GETINFO_GLYPHSTRING, print.getinfo_glyphstring, print_unidrv-pscript_rendering_5b2786d4-2633-4abe-8eaf-23e7100f7ba3.xml, printoem/GETINFO_GLYPHSTRING, printoem/PGETINFO_GLYPHSTRING"
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: GETINFO_GLYPHSTRING, *PGETINFO_GLYPHSTRING
f1_keywords:
 - _GETINFO_GLYPHSTRING
 - printoem/_GETINFO_GLYPHSTRING
 - PGETINFO_GLYPHSTRING
 - printoem/PGETINFO_GLYPHSTRING
 - GETINFO_GLYPHSTRING
 - printoem/GETINFO_GLYPHSTRING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - GETINFO_GLYPHSTRING
---

# _GETINFO_GLYPHSTRING structure


## -description

The GETINFO_GLYPHSTRING structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function.

## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the GETINFO_GLYPHSTRING structure. This value is supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> caller.

### -field dwCount

Specifies the number of elements in the arrays pointed to by <b>pGlyphIn</b> and <b>pGlyphOut</b>. This value is supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> caller.

### -field dwTypeIn

Specifies the type of glyph specifier array pointed to by <b>pGlyphIn</b>. Valid values are as follows:

<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
TYPE_GLYPHHANDLE

</td>
<td>
The <b>pGlyphIn</b> array elements are of type HGLYPH, or handle to a device font glyph. For this value of <b>dwTypeIn</b>, valid values for <b>dwTypeOut</b> are either TYPE_UNICODE or TYPE_TRANSDATA.

</td>
</tr>
<tr>
<td>
TYPE_GLYPHID

</td>
<td>
The <b>pGlyphIn</b> array elements are of type DWORD, and contain glyph identifiers for downloaded TrueType font glyphs. For this value of <b>dwTypeIn</b>, valid values for <b>dwTypeOut</b> are either TYPE_UNICODE or TYPE_GLYPHHANDLE.

</td>
</tr>
</table>
 

Supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> caller.

### -field pGlyphIn

Pointer to an array of glyph specifiers. The array element type is indicated by <b>dwTypeIn</b>. This value is supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> caller.

### -field dwTypeOut

Specifies the type of glyph specifier array pointed to by <b>pGlyphOut</b>. Valid values are as follows:

<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
TYPE_GLYPHHANDLE

</td>
<td>
The <b>pGlyphOut</b> array elements are of type HGLYPH, or handle to a device font glyph. This value is valid only when <b>dwTypeIn</b> has been set to TYPE_GLYPHID.

</td>
</tr>
<tr>
<td>
TYPE_TRANSDATA

</td>
<td>
The <b>pGlyphOut</b> array elements are of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_transdata">TRANSDATA</a>. This value is valid only when <b>dwTypeIn</b> has been set to TYPE_GLYPHHANDLE.

</td>
</tr>
<tr>
<td>
TYPE_UNICODE

</td>
<td>
The <i>pGlyph</i> array elements are of type WCHAR. This value is valid when <b>dwTypeIn</b> has been set to either TYPE_GLYPHHANDLE or TYPE_GLYPHID.

</td>
</tr>
</table>
 

Supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> caller.

### -field pGlyphOut

Caller-supplied pointer to an empty array of glyph specifiers. The array is filled in by Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function. The array element type is indicated by <b>dwTypeOut</b>. This pointer is supplied by the <u>UNIFONTOBJ_GetInfo</u> caller.

### -field dwGlyphOutSize

Specifies the size, in bytes, of the buffer pointed to by <b>pGlyphOut</b>. This member is used only when <b>dwTypeIn</b> has been set to TYPE_GLYPHHANDLE and <b>dwTypeOut</b> has been set to TYPE_TRANSDATA. See the following Remarks section for more information.

## -remarks

To convert an array of glyph specifiers from one type to another, a rendering plug-in can supply the address of a GETINFO_GLYPHSTRING structure when calling Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function.

If the conversion is from TYPE_GLYPHHANDLE to TYPE_TRANSDATA, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> must be called twice.

<ol>
<li>
Before the first call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a>, the rendering plug-in fills in the <b>dwSize</b>, <b>dwCount</b>, <b>dwTypeIn</b>, and <b>pGlyphIn</b> members and sets <b>dwGlyphOutSize</b> member to zero. 

After <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> returns, the <b>dwGlyphOutSize</b> member contains the size, in bytes, of the buffer needed to store the converted string.

</li>
<li>
The plug-in allocates a block of memory of the size received in the <b>dwGlyphOutSize</b> member, sets the <b>pGlyphOut</b> member to point to this memory block, and calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> once more. UNIDRV then converts the string from TYPE_GLYPHHANDLE to TYPE_TRANSDATA.

</li>
</ol>
The values that a rendering plug-in specifies for the <b>dwTypeIn </b>and <b>pGlyphIn</b> members typically are those that were previously received as the <b>dwType </b>and <i>pGlyph</i> parameters to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-outputcharstr">IPrintOemUni::OutputCharStr</a> method.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-outputcharstr">IPrintOemUni::OutputCharStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a>

