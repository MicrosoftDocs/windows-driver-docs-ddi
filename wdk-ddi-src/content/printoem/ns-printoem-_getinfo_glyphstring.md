---
UID: NS:printoem._GETINFO_GLYPHSTRING
title: "_GETINFO_GLYPHSTRING"
author: windows-driver-content
description: The GETINFO_GLYPHSTRING structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_glyphstring.htm
old-project: print
ms.assetid: ebcc1ada-af6f-46c3-a025-97079eb08816
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: GETINFO_GLYPHSTRING, GETINFO_GLYPHSTRING structure [Print Devices], print_unidrv-pscript_rendering_5b2786d4-2633-4abe-8eaf-23e7100f7ba3.xml, _GETINFO_GLYPHSTRING, printoem/PGETINFO_GLYPHSTRING, PGETINFO_GLYPHSTRING structure pointer [Print Devices], print.getinfo_glyphstring, *PGETINFO_GLYPHSTRING, printoem/GETINFO_GLYPHSTRING, PGETINFO_GLYPHSTRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	GETINFO_GLYPHSTRING
product: Windows
targetos: Windows
req.typenames: GETINFO_GLYPHSTRING, *PGETINFO_GLYPHSTRING
req.product: Windows 10 or later.
---

# _GETINFO_GLYPHSTRING structure


## -description


The GETINFO_GLYPHSTRING structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.


## -syntax


````
typedef struct _GETINFO_GLYPHSTRING {
  DWORD dwSize;
  DWORD dwCount;
  DWORD dwTypeIn;
  PVOID pGlyphIn;
  DWORD dwTypeOut;
  PVOID pGlyphOut;
  DWORD dwGlyphOutSize;
} GETINFO_GLYPHSTRING, *PGETINFO_GLYPHSTRING;
````


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the GETINFO_GLYPHSTRING structure. This value is supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field dwCount

Specifies the number of elements in the arrays pointed to by <b>pGlyphIn</b> and <b>pGlyphOut</b>. This value is supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


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
 

Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field pGlyphIn

Pointer to an array of glyph specifiers. The array element type is indicated by <b>dwTypeIn</b>. This value is supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


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
The <b>pGlyphOut</b> array elements are of type <a href="..\prntfont\ns-prntfont-_transdata.md">TRANSDATA</a>. This value is valid only when <b>dwTypeIn</b> has been set to TYPE_GLYPHHANDLE.

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
 

Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field pGlyphOut

Caller-supplied pointer to an empty array of glyph specifiers. The array is filled in by Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function. The array element type is indicated by <b>dwTypeOut</b>. This pointer is supplied by the <u>UNIFONTOBJ_GetInfo</u> caller.


### -field dwGlyphOutSize

Specifies the size, in bytes, of the buffer pointed to by <b>pGlyphOut</b>. This member is used only when <b>dwTypeIn</b> has been set to TYPE_GLYPHHANDLE and <b>dwTypeOut</b> has been set to TYPE_TRANSDATA. See the following Remarks section for more information.


## -remarks



To convert an array of glyph specifiers from one type to another, a rendering plug-in can supply the address of a GETINFO_GLYPHSTRING structure when calling Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.

If the conversion is from TYPE_GLYPHHANDLE to TYPE_TRANSDATA, <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> must be called twice.

<ol>
<li>
Before the first call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>, the rendering plug-in fills in the <b>dwSize</b>, <b>dwCount</b>, <b>dwTypeIn</b>, and <b>pGlyphIn</b> members and sets <b>dwGlyphOutSize</b> member to zero. 

After <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> returns, the <b>dwGlyphOutSize</b> member contains the size, in bytes, of the buffer needed to store the converted string.

</li>
<li>
The plug-in allocates a block of memory of the size received in the <b>dwGlyphOutSize</b> member, sets the <b>pGlyphOut</b> member to point to this memory block, and calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> once more. UNIDRV then converts the string from TYPE_GLYPHHANDLE to TYPE_TRANSDATA.

</li>
</ol>
The values that a rendering plug-in specifies for the <b>dwTypeIn </b>and <b>pGlyphIn</b> members typically are those that were previously received as the <b>dwType </b>and <i>pGlyph</i> parameters to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554267">IPrintOemUni::OutputCharStr</a> method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554267">IPrintOemUni::OutputCharStr</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GETINFO_GLYPHSTRING structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

