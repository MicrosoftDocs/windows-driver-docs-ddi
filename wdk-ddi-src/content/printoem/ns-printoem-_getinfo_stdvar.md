---
UID: NS:printoem._GETINFO_STDVAR
title: _GETINFO_STDVAR (printoem.h)
description: The GETINFO_STDVAR structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_stdvar.htm
tech.root: print
ms.assetid: 9f2ae88c-34a4-46b3-9571-5f2f023b7d6b
ms.date: 04/20/2018
keywords: ["_GETINFO_STDVAR structure"]
ms.keywords: "*PGETINFO_STDVAR, GETINFO_STDVAR, GETINFO_STDVAR structure [Print Devices], PGETINFO_STDVAR, PGETINFO_STDVAR structure pointer [Print Devices], _GETINFO_STDVAR, print.getinfo_stdvar, print_unidrv-pscript_rendering_3a08d48b-215f-4acc-89ef-849a2b826ce7.xml, printoem/GETINFO_STDVAR, printoem/PGETINFO_STDVAR"
f1_keywords:
 - "printoem/GETINFO_STDVAR"
 - "GETINFO_STDVAR"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- printoem.h
api_name:
- GETINFO_STDVAR
targetos: Windows
req.typenames: GETINFO_STDVAR, *PGETINFO_STDVAR
---

# _GETINFO_STDVAR structure


## -description


The GETINFO_STDVAR structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function.


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the GETINFO_STDVAR structure. Supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> caller.


### -field dwNumOfVariable


### -field dwStdVarID

 


### -field lStdVariable

 


### -field StdVar

Is an array specifying standard variable indexes and values. Each array element contains two members: a <b>dwStdVarID</b> member and an <b>lStdVariable</b> member.



#### dwStdVarID

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/standard-variables">standard variables</a> for which a value should be returned. Supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> caller. Valid values are contained in the following table.

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
 

Supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> caller.



#### lStdVariable

Specifies the current value of the specified standard variable. Supplied by Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function.


## -remarks



To obtain the current value for one or more of Unidrv's standard variables, a rendering plug-in can supply the address of a GETINFO_STDVAR structure when calling Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function.

For more information about <a href="https://docs.microsoft.com/windows-hardware/drivers/print/standard-variables">standard variables</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/microsoft-universal-printer-driver">Microsoft Universal Printer Driver</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a>
 

 

