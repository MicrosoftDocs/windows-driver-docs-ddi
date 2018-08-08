---
UID: NS:printoem._GETINFO_STDVAR
title: "_GETINFO_STDVAR"
author: windows-driver-content
description: The GETINFO_STDVAR structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_stdvar.htm
tech.root: print
ms.assetid: 9f2ae88c-34a4-46b3-9571-5f2f023b7d6b
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: "*PGETINFO_STDVAR, GETINFO_STDVAR, GETINFO_STDVAR structure [Print Devices], PGETINFO_STDVAR, PGETINFO_STDVAR structure pointer [Print Devices], _GETINFO_STDVAR, print.getinfo_stdvar, print_unidrv-pscript_rendering_3a08d48b-215f-4acc-89ef-849a2b826ce7.xml, printoem/GETINFO_STDVAR, printoem/PGETINFO_STDVAR"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	GETINFO_STDVAR
product:
- Windows
targetos: Windows
req.typenames: GETINFO_STDVAR, *PGETINFO_STDVAR
---

# _GETINFO_STDVAR structure


## -description


The GETINFO_STDVAR structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the GETINFO_STDVAR structure. Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field dwNumOfVariable


### -field dwStdVarID

 


### -field lStdVariable

 


### -field StdVar

Is an array specifying standard variable indexes and values. Each array element contains two members: a <b>dwStdVarID</b> member and an <b>lStdVariable</b> member.



#### dwStdVarID

Specifies the <a href="https://msdn.microsoft.com/d3f85c0f-7387-4301-8b1e-904471aed4b0">standard variables</a> for which a value should be returned. Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller. Valid values are contained in the following table.

<table>
<tr>
<th>Identifier</th>
<th>Standard Variable</th>
</tr>
<tr>
<td>
FNT_INFO_CURRENTFONTID

</td>
<td>
<code>CurrentFontID</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_FONTBOLD

</td>
<td>
<code>FontBold</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_FONTHEIGHT

</td>
<td>
<code>FontHeight</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_FONTITALIC

</td>
<td>
<code>FontItalic</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_FONTMAXWIDTH

</td>
<td>
<code>FontMaxWidth</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_FONTSTRIKETHRU

</td>
<td>
<code>FontStrikeThru</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_FONTUNDERLINE

</td>
<td>
<code>FontUnderline</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_FONTWIDTH

</td>
<td>
<code>FontWidth</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_GRAYPERCENTAGE

</td>
<td>
<code>GrayPercentage</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_NEXTFONTID

</td>
<td>
<code>NextFontID</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_NEXTGLYPH

</td>
<td>
<code>NextGlyph</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_PRINTDIRINCCDEGREES

</td>
<td>
<code>PrintDirInCCDegrees</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_TEXTXRES

</td>
<td>
<code>TextXRes</code>

</td>
</tr>
<tr>
<td>
FNT_INFO_TEXTYRES

</td>
<td>
<code>TextYRes</code>

</td>
</tr>
</table>
 

Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.



#### lStdVariable

Specifies the current value of the specified standard variable. Supplied by Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.


## -remarks



To obtain the current value for one or more of Unidrv's standard variables, a rendering plug-in can supply the address of a GETINFO_STDVAR structure when calling Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.

For more information about <a href="https://msdn.microsoft.com/d3f85c0f-7387-4301-8b1e-904471aed4b0">standard variables</a>, see <a href="https://msdn.microsoft.com/1f5d68a1-3552-44a9-a0c5-b3ec5fe22a22">Microsoft Universal Printer Driver</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>
 

 

