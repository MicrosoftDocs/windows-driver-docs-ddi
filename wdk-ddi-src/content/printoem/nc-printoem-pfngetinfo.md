---
UID: NC:printoem.PFNGETINFO
title: PFNGETINFO (printoem.h)
description: The UNIFONTOBJ_GetInfo callback function is provided by the Unidrv driver so that rendering plug-ins can obtain font or glyph information.
old-location: print\unifontobj_getinfo.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["PFNGETINFO callback function"]
ms.keywords: PFNGETINFO, UNIFONTOBJ_GetInfo, UNIFONTOBJ_GetInfo routine [Print Devices], print.unifontobj_getinfo, print_unidrv-pscript_rendering_7dc55246-beaa-4058-87a3-5438db3368c4.xml, printoem/UNIFONTOBJ_GetInfo
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFNGETINFO
 - printoem/PFNGETINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - PFNGETINFO
---

# PFNGETINFO callback function


## -description

The <b>UNIFONTOBJ_GetInfo</b> callback function is provided by the Unidrv driver so that rendering plug-ins can obtain font or glyph information.

## -parameters

### -param 

### -param Arg1

### -param Arg2

### -param Arg3

### -param Arg4

#### - dwDataSize

Specifies the size, in bytes, of the buffer pointed to by <i>pData</i>. Supplied by the caller.


#### - dwInfoID

Specifies the type of structure pointed to by <i>pData</i>. Supplied by the caller. See the following table.


#### - pData

Pointer to a structure, as indicated in the following table. Supplied by the caller.

<table>
<tr>
<th>dwInfoID Value</th>
<th><i>pData</i> Structure</th>
</tr>
<tr>
<td>
UFO_GETINFO_FONTOBJ

</td>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_fontobj">GETINFO_FONTOBJ</a>


</td>
</tr>
<tr>
<td>
UFO_GETINFO_GLYPHBITMAP

</td>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_glyphbitmap">GETINFO_GLYPHBITMAP</a>


</td>
</tr>
<tr>
<td>
UFO_GETINFO_GLYPHSTRING

</td>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_glyphstring">GETINFO_GLYPHSTRING</a>


</td>
</tr>
<tr>
<td>
UFO_GETINFO_GLYPHWIDTH

</td>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_glyphwidth">GETINFO_GLYPHWIDTH</a>


</td>
</tr>
<tr>
<td>
UFO_GETINFO_MEMORY

</td>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_memory">GETINFO_MEMORY</a>


</td>
</tr>
<tr>
<td>
UFO_GETINFO_STDVARIABLE

</td>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_stdvar">GETINFO_STDVAR</a>


</td>
</tr>
</table>
 

For a summary of structure contents, see the following <b>Remarks</b> section.


#### - pUFObj

Pointer to the <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_unifontobj">UNIFONTOBJ</a> structure received by the function that is making the callback to <b>UNIFONTOBJ_GetInfo</b>. Supplied by the caller.


#### - pcbNeeded

Pointer to a location that receives the minimum buffer size, in bytes, required to contain the structure identified by <i>dwInfoID</i>. Supplied by the caller.

## -returns

If the operation succeeds, the function returns <b>TRUE</b>. Otherwise it returns <b>FALSE</b>.

## -remarks

The <b>UNIFONTOBJ_GetInfo</b> callback function allows a <a href="/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-in</a> to call back into Unidrv to obtain font or glyph information from GDI, needed for handling <a href="/windows-hardware/drivers/print/customized-font-management">customized font management</a> operations.

A rendering plug-in receives the <b>UNIFONTOBJ_GetInfo</b> function's address in the <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_unifontobj">UNIFONTOBJ</a> structure that is passed to the font customization methods.

The type of information returned by the function is dependent on the input arguments. The caller supplies values for <i>dwInfoID</i>, <i>pData</i>, and <i>dwDataSize</i> to indicate the type of information wanted. The following table summarizes the types of information returned. For more information, see the structure descriptions.

<table>
<tr>
<th><i>pData</i> Structure</th>
<th>Returned Information</th>
</tr>
<tr>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_fontobj">GETINFO_FONTOBJ</a>


</td>
<td>
A FONTOBJ structure describing the current font.

</td>
</tr>
<tr>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_glyphbitmap">GETINFO_GLYPHBITMAP</a>


</td>
<td>
A single glyph bitmap.

</td>
</tr>
<tr>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_glyphstring">GETINFO_GLYPHSTRING</a>


</td>
<td>
An array of glyph specifiers in a specified format.

</td>
</tr>
<tr>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_glyphwidth">GETINFO_GLYPHWIDTH</a>


</td>
<td>
Total width of a set of glyphs.

</td>
</tr>
<tr>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_memory">GETINFO_MEMORY</a>


</td>
<td>
Amount of available printer memory remaining.

</td>
</tr>
<tr>
<td>

<a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_getinfo_stdvar">GETINFO_STDVAR</a>


</td>
<td>
The current value for one or more of Unidrv's <a href="/windows-hardware/drivers/print/standard-variables">standard variables</a>.

</td>
</tr>
</table>
 

If the buffer described by <i>pData</i> and <i>dwDataSize</i> is too small to receive the structure indicated by <i>dwInfoID</i>, the function loads the required buffer size into the location pointed by <i>pcbNeeded</i> and returns <b>FALSE</b>.

