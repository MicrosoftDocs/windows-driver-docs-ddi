---
UID: NS:prntfont._TRANSDATA
title: TRANSDATA (prntfont.h)
description: The TRANSDATA structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
tech.root: print
ms.date: 03/08/2023
keywords: ["TRANSDATA structure"]
ms.keywords: "*PTRANSDATA, PTRANSDATA, PTRANSDATA structure pointer [Print Devices], TRANSDATA, TRANSDATA structure [Print Devices], _TRANSDATA, print.transdata, print_unidrv-pscript_fonts_e41871c1-fc38-460e-b9e7-1df0564933e1.xml, prntfont/PTRANSDATA, prntfont/TRANSDATA"
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
req.typenames: TRANSDATA, *PTRANSDATA
f1_keywords:
 - _TRANSDATA
 - prntfont/_TRANSDATA
 - PTRANSDATA
 - prntfont/PTRANSDATA
 - TRANSDATA
 - prntfont/TRANSDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - prntfont.h
api_name:
 - _TRANSDATA
 - PTRANSDATA
 - TRANSDATA
---

## -description

The TRANSDATA structure is one of the structures used to define the contents of [glyph translation table files](/windows-hardware/drivers/print/customized-font-management) (.gtt files).

## -struct-fields

### -field ubCodePageID

Specifies the zero-based index of a particular structure in the array of [**UNI_CODEPAGEINFO**](./ns-prntfont-_uni_codepageinfo.md) structures. The first structure in this array has an index of 0, the second structure has an index of 1, and so on.

The **loCodePageOffset** member of the [**UNI_GLYPHSETDATA**](./ns-prntfont-_uni_glyphsetdata.md) structure contains the offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of the array of UNI_CODEPAGEINFO structures.

### -field ubType

Is a set of one or more bit flags, as follows:

One of the following three format flags can be set:

| Flag | Format |
|---|---|
| MTYPE_COMPOSE | The **sCode** member of the **uCode** union contains an offset to a string. The string contains a command to be sent to the printer. |
| MTYPE_DIRECT | The **ubCode** member of the **uCode** union contains a one-byte character code to be sent to the printer. |
| MTYPE_PAIRED | The **ubPairs** member of the **uCode** union contains a two-byte character code to be sent to the printer. |

One of the action following flags can be set. All are optional. Not valid if the **lPredefinedID** member of the [**UNI_GLYPHSETDATA**](./ns-prntfont-_uni_glyphsetdata.md) structure is set to CC_NOPRECNV.

| Flag | Action |
|---|---|
| MTYPE_ADD | The specified mapping is added to the map table contained in the .gtt file specified by the **lPredefinedID** member of the UNI_GLYPHSETDATA structure. |
| MTYPE_DISABLE | The specified mapping, contained in the .gtt file specified by the **lPredefinedID** member of the [**UNI_GLYPHSETDATA**](./ns-prntfont-_uni_glyphsetdata.md) structure, is disabled. |
| MTYPE_REPLACE | The specified mapping replaces mapping in the map table contained in the .gtt file specified by the **lPredefinedID** member of the UNI_GLYPHSETDATA structure. |

One of the following East Asian flags can be set:

| Flag | East Asian Format |
|---|---|
| MTYPE_SINGLE | Character data is single-byte. |
| MTYPE_DOUBLE | Character data is double-byte. |

### -field uCode

### -field uCode.sCode

Specifies the offset to a command string. The offset is relative to the beginning of the [**MAPTABLE**](./ns-prntfont-_maptable.md) structure containing the TRANSDATA array. The first word of the command string must be the command size. Valid if the MTYPE_COMPOSE flag is set in **uType**.

### -field uCode.ubCode

Specifies a one-byte character code. Valid if the MTYPE_DIRECT flag is set in **uType**.

### -field uCode.ubPairs

Specifies a two-byte character code. Valid if the MTYPE_PAIRED flag is set in **uType**.

## -remarks

A .gtt file's TRANSDATA structure array, which contains glyph mapping information, is contained in the file's [**MAPTABLE**](./ns-prntfont-_maptable.md) structure.

## -see-also

[**MAPTABLE**](./ns-prntfont-_maptable.md)

[**UNI_CODEPAGEINFO**](./ns-prntfont-_uni_codepageinfo.md)

[**UNI_GLYPHSETDATA**](./ns-prntfont-_uni_glyphsetdata.md)