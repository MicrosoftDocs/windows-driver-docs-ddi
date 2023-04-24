---
UID: NS:prntfont._UFF_FILEHEADER
title: UFF_FILEHEADER (prntfont.h)
description: The UFF_FILEHEADER structure is used to define the contents of Unidrv font format files (.uff files).
tech.root: print
ms.date: 03/08/2023
keywords: ["UFF_FILEHEADER structure"]
ms.keywords: "*PUFF_FILEHEADER, PUFF_FILEHEADER, PUFF_FILEHEADER structure pointer [Print Devices], UFF_FILEHEADER, UFF_FILEHEADER structure [Print Devices], _UFF_FILEHEADER, print.uff_fileheader, print_unidrv-pscript_fonts_a51bc6b1-df89-423f-83e8-9fad0cd20729.xml, prntfont/PUFF_FILEHEADER, prntfont/UFF_FILEHEADER"
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
req.typenames: UFF_FILEHEADER, *PUFF_FILEHEADER
f1_keywords:
 - _UFF_FILEHEADER
 - prntfont/_UFF_FILEHEADER
 - PUFF_FILEHEADER
 - prntfont/PUFF_FILEHEADER
 - UFF_FILEHEADER
 - prntfont/UFF_FILEHEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - prntfont.h
api_name:
 - _UFF_FILEHEADER
 - PUFF_FILEHEADER
 - UFF_FILEHEADER
---

## -description

The UFF_FILEHEADER structure is used to define the contents of [Unidrv font format files](/windows-hardware/drivers/print/customized-font-management) (.uff files).

## -struct-fields

### -field dwSignature

Specifies the signature for .uff files. This value must be UFF_FILE_MAGIC.

### -field dwVersion

Specifies the format version for .uff files. This value must be UFF_VERSION_NUMBER. The HIWORD contains the major version number and the LOWORD contains the minor version number.

### -field dwSize

Specifies the size, in bytes, of the UFF_FILEHEADER structure.

### -field nFonts

Specifies the number of fonts specified within the .uff file and identified by [**DATA_HEADER**](./ns-prntfont-_data_header.md) structures. This is also the number of [**UFF_FONTDIRECTORY**](./ns-prntfont-_uff_fontdirectory.md) structures within the .uff file.

### -field nGlyphSets

Specifies the  number of glyph sets specified within the .uff file and identified by DATA_HEADER structures. Some fonts might share a glyph set.

### -field nVarData

Specifies the  number of variable data sections specified within the .uff file and identified by DATA_HEADER structures.

### -field offFontDir

Specifies the offset, in bytes, from the beginning of the .uff file to the beginning of the first [**UFF_FONTDIRECTORY**](./ns-prntfont-_uff_fontdirectory.md) structure.

### -field dwFlags

Is a set of bit flags, as specified in the following table.

| Flag | Definition |
|---|---|
| FONT_DIR_SORTED | The array of UFF_FONTDIRECTORY structures (specified by **offFontDir**) is sorted by the contents of that structure's **wFontID** member. |

### -field dwReserved

Reserved. Must be set to zero.

## -see-also

[**DATA_HEADER**](./ns-prntfont-_data_header.md)

[**UFF_FONTDIRECTORY**](./ns-prntfont-_uff_fontdirectory.md)