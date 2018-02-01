---
UID: NS:printoem._GETINFO_STDVAR
title: "_GETINFO_STDVAR"
author: windows-driver-content
description: The GETINFO_STDVAR structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_stdvar.htm
old-project: print
ms.assetid: 9f2ae88c-34a4-46b3-9571-5f2f023b7d6b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.getinfo_stdvar, print_unidrv-pscript_rendering_3a08d48b-215f-4acc-89ef-849a2b826ce7.xml, GETINFO_STDVAR structure [Print Devices], _GETINFO_STDVAR, *PGETINFO_STDVAR, GETINFO_STDVAR, PGETINFO_STDVAR structure pointer [Print Devices], printoem/PGETINFO_STDVAR, PGETINFO_STDVAR, printoem/GETINFO_STDVAR
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
-	GETINFO_STDVAR
product: Windows
targetos: Windows
req.typenames: "*PGETINFO_STDVAR, GETINFO_STDVAR"
req.product: Windows 10 or later.
---

# _GETINFO_STDVAR structure


## -description


The GETINFO_STDVAR structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.


## -syntax


````
typedef struct _GETINFO_STDVAR {
  DWORD  dwSize;
  DWORD  dwNumOfVariable;
  struct {
    DWORD dwStdVarID;
    LONG  lStdVariable;
  } StdVar[1];
} GETINFO_STDVAR, *PGETINFO_STDVAR;
````


## -struct-fields




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


### -field dwSize

Specifies the size, in bytes, of the GETINFO_STDVAR structure. Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field dwNumOfVariable



## -remarks


To obtain the current value for one or more of Unidrv's standard variables, a rendering plug-in can supply the address of a GETINFO_STDVAR structure when calling Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.

For more information about <a href="https://msdn.microsoft.com/d3f85c0f-7387-4301-8b1e-904471aed4b0">standard variables</a>, see <a href="https://msdn.microsoft.com/1f5d68a1-3552-44a9-a0c5-b3ec5fe22a22">Microsoft Universal Printer Driver</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GETINFO_STDVAR structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

