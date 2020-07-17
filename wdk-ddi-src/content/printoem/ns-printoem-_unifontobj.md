---
UID: NS:printoem._UNIFONTOBJ
title: _UNIFONTOBJ (printoem.h)
description: The UNIFONTOBJ structure is used as an input parameter to font functions in rendering plug-ins.
old-location: print\unifontobj.htm
tech.root: print
ms.assetid: ff3ecef2-abf2-4ecb-b4af-81e6c6d8fb4c
ms.date: 04/20/2018
keywords: ["_UNIFONTOBJ structure"]
ms.keywords: "*PUNIFONTOBJ, PUNIFONTOBJ, PUNIFONTOBJ structure pointer [Print Devices], UNIFONTOBJ, UNIFONTOBJ structure [Print Devices], _UNIFONTOBJ, print.unifontobj, print_unidrv-pscript_rendering_05a25ef3-5ce2-43f5-ae35-790691bda143.xml, printoem/PUNIFONTOBJ, printoem/UNIFONTOBJ"
f1_keywords:
 - "printoem/UNIFONTOBJ"
 - "UNIFONTOBJ"
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
- UNIFONTOBJ
product:
- Windows
targetos: Windows
req.typenames: UNIFONTOBJ, *PUNIFONTOBJ
---

# _UNIFONTOBJ structure


## -description


The UNIFONTOBJ structure is used as an input parameter to font functions in rendering plug-ins.


## -struct-fields




### -field ulFontID

Specifies a resource identifier for an RC_UFM resource contained in a Unidrv minidriver's resource DLL. Supplied by Unidrv.


### -field dwFlags

Is a set of Unidrv-supplied bit flags. Flag definitions are as follows:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
UFOFLAG_TTDOWNLOAD_BITMAP

</td>
<td>
If set, the font is a bitmap font.

</td>
</tr>
<tr>
<td>
UFOFLAG_TTDOWNLOAD_TTOUTLINE

</td>
<td>
If set, the font is a TrueType outline font.

</td>
</tr>
<tr>
<td>
UFOFLAG_TTFONT

</td>
<td>
If set, the font is a downloadable TrueType font.

If not set, the font is a device font.

</td>
</tr>
<tr>
<td>
UFOFLAG_TTOUTLINE_BOLD_SIM

</td>
<td>
If set, the TrueType font has bold simulation done by GDI.

</td>
</tr>
<tr>
<td>
UFOFLAG_TTOUTLINE_ITALIC_SIM

</td>
<td>
If set, the TrueType font has italic simulation done by GDI.

</td>
</tr>
<tr>
<td>
UFOFLAG_TTOUTLINE_VERTICAL

</td>
<td>
If set, the TrueType font is a vertical font. Note that this flag is available only for those Asian fonts that can be written vertically.

If not set, text is written horizontally.

</td>
</tr>
<tr>
<td>
UFOFLAG_TTSUBSTITUTED

</td>
<td>
If set, the device font is a font substituted for the TrueType font. In the font substitution, GDI requests that Unidrv print using a TrueType font. For performance reasons, Unidrv substitutes a device font for the TrueType font. (The substitution is specified by a <a href="https://docs.microsoft.com/windows-hardware/drivers/">generic printer description (GPD)</a> file or in a table in the registry.) For this substitution, for some printers, it is necessary to adjust the baseline position of the device font, because the baseline position of the device font can be higher than that of the TrueType font. The adjustment causes the output of the substituted device font to be shifted down to correct this discrepancy. Depending on the flags set in the UNIFONTOBJ structure, the printer minidriver is able to adjust the baseline position of device fonts.

</td>
</tr>
</table>
 


### -field pIFIMetrics

Pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_ifimetrics">IFIMETRICS</a> structure. Supplied by Unidrv.


### -field pfnGetInfo

Pointer to Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function. Supplied by Unidrv.


## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_ifimetrics">IFIMETRICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a>
 

 

