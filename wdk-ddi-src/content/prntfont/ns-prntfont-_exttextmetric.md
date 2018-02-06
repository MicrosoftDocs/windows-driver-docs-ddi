---
UID: NS:prntfont._EXTTEXTMETRIC
title: "_EXTTEXTMETRIC"
author: windows-driver-content
description: The EXTTEXTMETRIC structure is used to specify font-specific information within Unidrv font metrics files (.ufm files).
old-location: print\exttextmetric.htm
old-project: print
ms.assetid: d3d2397c-71c3-4904-a1ad-96a94698e50c
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: "_EXTTEXTMETRIC, EXTTEXTMETRIC, *PEXTTEXTMETRIC, print.exttextmetric, PEXTTEXTMETRIC structure pointer [Print Devices], prntfont/PEXTTEXTMETRIC, print_unidrv-pscript_fonts_8b9f67ef-9ab0-40e4-9474-c506de9c8824.xml, prntfont/EXTTEXTMETRIC, EXTTEXTMETRIC structure [Print Devices], PEXTTEXTMETRIC"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	prntfont.h
apiname:
-	EXTTEXTMETRIC
product: Windows
targetos: Windows
req.typenames: EXTTEXTMETRIC, *PEXTTEXTMETRIC
req.product: Windows 10 or later.
---

# _EXTTEXTMETRIC structure


## -description


The EXTTEXTMETRIC structure is used to specify font-specific information within <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv font metrics files</a> (.ufm files).


## -syntax


````
typedef struct _EXTTEXTMETRIC {
  short emSize;
  short emPointSize;
  short emOrientation;
  short emMasterHeight;
  short emMinScale;
  short emMaxScale;
  short emMasterUnits;
  short emCapHeight;
  short emXHeight;
  short emLowerCaseAscent;
  short emLowerCaseDescent;
  short emSlant;
  short emSuperScript;
  short emSubScript;
  short emSuperScriptSize;
  short emSubScriptSize;
  short emUnderlineOffset;
  short emUnderlineWidth;
  short emDoubleUpperUnderlineOffset;
  short emDoubleLowerUnderlineOffset;
  short emDoubleUpperUnderlineWidth;
  short emDoubleLowerUnderlineWidth;
  short emStrikeOutOffset;
  short emStrikeOutWidth;
  WORD  emKernPairs;
  WORD  emKernTracks;
} EXTTEXTMETRIC, *PEXTTEXTMETRIC;
````


## -struct-fields




### -field emSize

Specifies the size of the structure, in bytes.


### -field emPointSize

Specifies the nominal point size of this font, in twips (1/20 of a point, or 1/1440 inch). This is the intended size of the font; the actual size may differ slightly depending on the resolution of the device.


### -field emOrientation

Specifies the orientation of the font. The <b>emOrientation</b> member can be any of the following values: 
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
Either portrait or landscape orientation 

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Portrait orientation

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Landscape orientation

</td>
</tr>
</table> 


### -field emMasterHeight

Specifies the font size, in device units, for which the values in this font's extent table are exact.


### -field emMinScale

Specifies the minimum valid point size for this font. The following equation illustrates how the minimum point size is determined:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>smallest point size = (emMinScale * 72) / dfVertRes </pre>
</td>
</tr>
</table></span></div>The value 72 represents the number of points per inch. The <i>dfVertRes</i> value is the number of dots per inch.


### -field emMaxScale

Specifies the maximum valid point size for this font. The following equation illustrates how the maximum point size is determined:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>largest point size = (etmMaxScale * 72) / dfVertRes </pre>
</td>
</tr>
</table></span></div>The value 72 represents the number of points per inch. The <i>dfVertRes</i> value is the number of dots per inch.


### -field emMasterUnits

Specifies the integral number of units per em, where an em equals the value of the <b>emMasterHeight</b> member. (That is, <b>emMasterUnits</b> is <b>emMasterHeight</b> expressed in font units instead of device units.)


### -field emCapHeight

Specifies the height, in font units, of uppercase characters in the font. Typically, this is the height of uppercase H.


### -field emXHeight

Specifies the height, in font units, of lowercase characters in the font. Typically, this is the height of lowercase x.


### -field emLowerCaseAscent

Specifies the distance, in font units, that the ascender of lowercase letters extends above the base line. Typically, this is the height of lowercase d.


### -field emLowerCaseDescent

Specifies the distance, in font units, that the descender of lowercase letters extends below the base line. Typically, this is specified for the descender of lowercase p.


### -field emSlant

For an italic or slanted font, specifies the angle of the slant measured in tenths of a degree clockwise from the upright version of the font.


### -field emSuperScript

Specifies the recommended amount, in font units, to offset superscript characters from the base line. This is typically a negative value.


### -field emSubScript

Specifies the recommended amount, in font units, to offset subscript characters from the base line. This is typically a positive value.


### -field emSuperScriptSize

Specifies the recommended size, in font units, of superscript characters for this font.


### -field emSubScriptSize

Specifies the recommended size, in font units, of subscript characters for this font.


### -field emUnderlineOffset

Specifies the offset, in font units, downward from the base line, where the top of a single underline bar should appear.


### -field emUnderlineWidth

Specifies the thickness, in font units, of the underline bar.


### -field emDoubleUpperUnderlineOffset

Specifies the offset, in font units, downward from the base line, where the top of the upper double-underline bar should appear.


### -field emDoubleLowerUnderlineOffset

Specifies the offset, in font units, downward from the base line, where the top of the lower double-underline bar should appear.


### -field emDoubleUpperUnderlineWidth

Specifies the thickness, in font units, of the upper underline bar.


### -field emDoubleLowerUnderlineWidth

Specifies the thickness, in font units, of the lower underline bar.


### -field emStrikeOutOffset

Specifies the offset, in font units, upward from the base line, where the top of a strikeout bar should appear.


### -field emStrikeOutWidth

Specifies the thickness, in font units, of the strikeout bar.


### -field emKernPairs

Specifies the number of character kerning pairs defined for this font.


### -field emKernTracks

Specifies the number of kerning tracks defined for this font.

