---
UID: NS:prntfont._UNIDRVINFO
title: "_UNIDRVINFO"
author: windows-driver-content
description: The UNIDRVINFO structure is used to specify printer-specific information within Unidrv font metrics files (.ufm files).
old-location: print\unidrvinfo.htm
old-project: print
ms.assetid: f57514ed-33b2-4895-aaba-5866b6fc01d2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PUNIDRVINFO, PUNIDRVINFO, PUNIDRVINFO structure pointer [Print Devices], UNIDRVINFO, UNIDRVINFO structure [Print Devices], _UNIDRVINFO, print.unidrvinfo, print_unidrv-pscript_fonts_b956aa02-1966-47c6-aec1-8ef8b98f4e57.xml, prntfont/PUNIDRVINFO, prntfont/UNIDRVINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prntfont.h
req.include-header: Prntfont.h
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
-	prntfont.h
api_name:
-	UNIDRVINFO
product: Windows
targetos: Windows
req.typenames: UNIDRVINFO, *PUNIDRVINFO
req.product: Windows 10 or later.
---

# _UNIDRVINFO structure


## -description


The UNIDRVINFO structure is used to specify printer-specific information within <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv font metrics files</a> (.ufm files).


## -syntax


````
typedef struct _UNIDRVINFO {
  DWORD dwSize;
  DWORD flGenFlags;
  WORD  wType;
  WORD  fCaps;
  WORD  wXRes;
  WORD  wYRes;
  short sYAdjust;
  short sYMoved;
  WORD  wPrivateData;
  short sShift;
  INVOC SelectFont;
  INVOC UnSelectFont;
  WORD  wReserved[4];
} UNIDRVINFO, *PUNIDRVINFO;
````


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the UNIDRVINFO structure.


### -field flGenFlags

Contains one or more bit flags describing font characteristics. The following flags are defined:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
UFM_CART

</td>
<td>
The font is contained in a cartridge.

</td>
</tr>
<tr>
<td>
UFM_SCALABLE

</td>
<td>
The font is scalable.

</td>
</tr>
<tr>
<td>
UFM_SOFT

</td>
<td>
The font is a soft font, requiring downloading.

</td>
</tr>
</table>
 


### -field wType

Contains an integer constant describing the font type. The following constants are defined: 

<table>
<tr>
<th>Constant</th>
<th>Definition</th>
</tr>
<tr>
<td>
DF_TYPE_CAPSL

</td>
<td>
Canon CAPSL scalable font

</td>
</tr>
<tr>
<td>
DF_TYPE_HPINTELLIFONT

</td>
<td>
HP Intellifont font

</td>
</tr>
<tr>
<td>
DF_TYPE_OEM1

</td>
<td>
OEM-supplied scalable font

</td>
</tr>
<tr>
<td>
DF_TYPE_OEM2

</td>
<td>
OEM-supplied scalable font

</td>
</tr>
<tr>
<td>
DF_TYPE_PST1

</td>
<td>
Lexmark PPDS scalable font

</td>
</tr>
<tr>
<td>
DF_TYPE_TRUETYPE

</td>
<td>
HP PCLETTO font for LJ4 printers

</td>
</tr>
</table>
 


### -field fCaps

Contains one or more bit flags identifying limitations on the capabilities provided by a device font. The following flags are defined:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
DF_BKSP_OK

</td>
<td>
If set, a single backspace character can move the cursor to the beginning of the overstrike region. If not set, an x-movement cursor command must be sent.

(Used only if MTYPE_PAIRED is specified for the character's <a href="..\prntfont\ns-prntfont-_transdata.md">TRANSDATA</a> structure in <a href="..\prntfont\ns-prntfont-_maptable.md">MAPTABLE</a>. Otherwise ignored.)

</td>
</tr>
<tr>
<td>
DF_NO_BOLD

</td>
<td>
The device font cannot be bolded using underline simulation.

</td>
</tr>
<tr>
<td>
DF_NO_DOUBLE_UNDERLINE

</td>
<td>
The device font cannot be double-underlined using double-underline simulation.

</td>
</tr>
<tr>
<td>
DF_NO_STRIKETHRU

</td>
<td>
The device font cannot be struck through using strike-through simulation.

</td>
</tr>
<tr>
<td>
DF_NOITALIC

</td>
<td>
The device font cannot be italicized using italic simulation.

</td>
</tr>
<tr>
<td>
DF_NOUNDER

</td>
<td>
The device font cannot be underlined using underline simulation.

</td>
</tr>
<tr>
<td>
DF_XM_CR

</td>
<td>
Unidrv must send a carriage return command after each line of text.

</td>
</tr>
</table>
 


### -field wXRes

Specifies the font's x-resolution.


### -field wYRes

Specifies the font's y-resolution.


### -field sYAdjust

Specifies the amount of vertical adjustment required before output of double-height characters on dot-matrix printers.


### -field sYMoved

Specifies the amount of vertical cursor movement that results when a double-height character is printed on a dot-matrix printer.


### -field wPrivateData

Can be used for printer-specific information such as, for example, HP DeskJet permutations.


### -field sShift

Specifies the number of pixels by which each character must be shifted. Used for the Microsoft Z1a cartridge.


### -field SelectFont

Is an <a href="..\prntfont\ns-prntfont-_invoc.md">INVOC</a> structure containing the printer's font selection command.


### -field UnSelectFont

Is an INVOC structure containing the printer's font deselection command.


### -field wReserved

Not used.


## -remarks



A .ufm (Unidrv Font Metrics) file's UNIDRVINFO structure is accessed by a pointer in the file's <a href="..\prntfont\ns-prntfont-_unifm_hdr.md">UNIFM_HDR</a> structure.




## -see-also

<a href="..\prntfont\ns-prntfont-_invoc.md">INVOC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20UNIDRVINFO structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

