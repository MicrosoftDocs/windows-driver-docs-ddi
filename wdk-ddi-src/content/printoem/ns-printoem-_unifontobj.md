---
UID: NS:printoem._UNIFONTOBJ
title: "_UNIFONTOBJ"
author: windows-driver-content
description: The UNIFONTOBJ structure is used as an input parameter to font functions in rendering plug-ins.
old-location: print\unifontobj.htm
old-project: print
ms.assetid: ff3ecef2-abf2-4ecb-b4af-81e6c6d8fb4c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.unifontobj, PUNIFONTOBJ structure pointer [Print Devices], print_unidrv-pscript_rendering_05a25ef3-5ce2-43f5-ae35-790691bda143.xml, *PUNIFONTOBJ, PUNIFONTOBJ, printoem/UNIFONTOBJ, _UNIFONTOBJ, UNIFONTOBJ, printoem/PUNIFONTOBJ, UNIFONTOBJ structure [Print Devices]
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
-	UNIFONTOBJ
product: Windows
targetos: Windows
req.typenames: UNIFONTOBJ, *PUNIFONTOBJ
req.product: Windows 10 or later.
---

# _UNIFONTOBJ structure


## -description


The UNIFONTOBJ structure is used as an input parameter to font functions in rendering plug-ins.


## -syntax


````
typedef struct _UNIFONTOBJ {
  ULONG      ulFontID;
  DWORD      dwFlags;
  IFIMETRICS *pIFIMetrics;
  PFNGETINFO pfnGetInfo;
} UNIFONTOBJ, *PUNIFONTOBJ;
````


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
If set, the device font is a font substituted for the TrueType font. In the font substitution, GDI requests that Unidrv print using a TrueType font. For performance reasons, Unidrv substitutes a device font for the TrueType font. (The substitution is specified by a <a href="https://msdn.microsoft.com/f67c673d-c6f0-49f0-850a-d8b00e99ddd4">generic printer description (GPD)</a> file or in a table in the registry.) For this substitution, for some printers, it is necessary to adjust the baseline position of the device font, because the baseline position of the device font can be higher than that of the TrueType font. The adjustment causes the output of the substituted device font to be shifted down to correct this discrepancy. Depending on the flags set in the UNIFONTOBJ structure, the printer minidriver is able to adjust the baseline position of device fonts.

</td>
</tr>
</table> 


### -field pIFIMetrics

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567418">IFIMETRICS</a> structure. Supplied by Unidrv.


### -field pfnGetInfo

Pointer to Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function. Supplied by Unidrv.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567418">IFIMETRICS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20UNIFONTOBJ structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

