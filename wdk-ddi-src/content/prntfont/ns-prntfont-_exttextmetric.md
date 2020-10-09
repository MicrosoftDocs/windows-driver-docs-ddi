---
UID: NS:prntfont._EXTTEXTMETRIC
title: _EXTTEXTMETRIC (prntfont.h)
description: The EXTTEXTMETRIC structure is used to specify font-specific information within Unidrv font metrics files (.ufm files).
old-location: print\exttextmetric.htm
tech.root: print
ms.assetid: d3d2397c-71c3-4904-a1ad-96a94698e50c
ms.date: 04/20/2018
keywords: ["EXTTEXTMETRIC structure"]
ms.keywords: "*PEXTTEXTMETRIC, EXTTEXTMETRIC, EXTTEXTMETRIC structure [Print Devices], PEXTTEXTMETRIC, PEXTTEXTMETRIC structure pointer [Print Devices], _EXTTEXTMETRIC, print.exttextmetric, print_unidrv-pscript_fonts_8b9f67ef-9ab0-40e4-9474-c506de9c8824.xml, prntfont/EXTTEXTMETRIC, prntfont/PEXTTEXTMETRIC"
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
targetos: Windows
req.typenames: EXTTEXTMETRIC, *PEXTTEXTMETRIC
f1_keywords:
 - _EXTTEXTMETRIC
 - prntfont/_EXTTEXTMETRIC
 - PEXTTEXTMETRIC
 - prntfont/PEXTTEXTMETRIC
 - EXTTEXTMETRIC
 - prntfont/EXTTEXTMETRIC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - prntfont.h
api_name:
 - EXTTEXTMETRIC
---

# _EXTTEXTMETRIC structure


## -description

The EXTTEXTMETRIC structure is used to specify font-specific information within [Unidrv font metrics files](/windows-hardware/drivers/print/customized-font-management) (.ufm files).

## -struct-fields

### -field emSize

Specifies the size of the structure, in bytes.

### -field emPointSize

Specifies the nominal point size of this font, in twips (1/20 of a point, or 1/1440 inch). This is the intended size of the font; the actual size may differ slightly depending on the resolution of the device.

### -field emOrientation

Specifies the orientation of the font. The **emOrientation** member can be any of the following values:

| Value | Meaning |
| --- | --- |
| 0 | Either portrait or landscape orientation |
| 1 | Portrait orientation |
| 2 | Landscape orientation |

### -field emMasterHeight

Specifies the font size, in device units, for which the values in this font's extent table are exact.

### -field emMinScale

Specifies the minimum valid point size for this font. The following equation illustrates how the minimum point size is determined:

```cpp
smallest point size = (emMinScale * 72) / dfVertRes
```

The value 72 represents the number of points per inch. The *dfVertRes* value is the number of dots per inch.

### -field emMaxScale

Specifies the maximum valid point size for this font. The following equation illustrates how the maximum point size is determined:

```cpp
largest point size = (etmMaxScale * 72) / dfVertRes
```

The value 72 represents the number of points per inch. The *dfVertRes* value is the number of dots per inch.

### -field emMasterUnits

Specifies the integral number of units per em, where an em equals the value of the **emMasterHeight** member. (That is, **emMasterUnits** is **emMasterHeight** expressed in font units instead of device units.)

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