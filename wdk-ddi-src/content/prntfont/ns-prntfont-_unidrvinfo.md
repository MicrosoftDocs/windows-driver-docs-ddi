---
UID: NS:prntfont._UNIDRVINFO
title: _UNIDRVINFO (prntfont.h)
description: The UNIDRVINFO structure is used to specify printer-specific information within Unidrv font metrics files (.ufm files).
tech.root: print
ms.date: 03/08/2023
keywords: ["UNIDRVINFO structure"]
ms.keywords: "*PUNIDRVINFO, PUNIDRVINFO, PUNIDRVINFO structure pointer [Print Devices], UNIDRVINFO, UNIDRVINFO structure [Print Devices], _UNIDRVINFO, print.unidrvinfo, print_unidrv-pscript_fonts_b956aa02-1966-47c6-aec1-8ef8b98f4e57.xml, prntfont/PUNIDRVINFO, prntfont/UNIDRVINFO"
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
req.typenames: UNIDRVINFO, *PUNIDRVINFO
f1_keywords:
 - _UNIDRVINFO
 - prntfont/_UNIDRVINFO
 - PUNIDRVINFO
 - prntfont/PUNIDRVINFO
 - UNIDRVINFO
 - prntfont/UNIDRVINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - prntfont.h
api_name:
 - _UNIDRVINFO
 - PUNIDRVINFO
 - UNIDRVINFO
---

## -description

The UNIDRVINFO structure is used to specify printer-specific information within [Unidrv font metrics files](/windows-hardware/drivers/print/customized-font-management) (.ufm files).

## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the UNIDRVINFO structure.

### -field flGenFlags

Contains one or more bit flags describing font characteristics. The following flags are defined:

| Flag | Definition |
|---|---|
| UFM_CART | The font is contained in a cartridge. |
| UFM_SCALABLE | The font is scalable. |
| UFM_SOFT | The font is a soft font, requiring downloading. |

### -field wType

Contains an integer constant describing the font type. The following constants are defined:

| Constant | Definition |
|---|---|
| DF_TYPE_CAPSL | Canon CAPSL scalable font |
| DF_TYPE_HPINTELLIFONT | HP Intellifont font |
| DF_TYPE_OEM1 | OEM-supplied scalable font |
| DF_TYPE_OEM2 | OEM-supplied scalable font |
| DF_TYPE_PST1 | Lexmark PPDS scalable font |
| DF_TYPE_TRUETYPE | HP PCLETTO font for LJ4 printers |

### -field fCaps

Contains one or more bit flags identifying limitations on the capabilities provided by a device font. The following flags are defined:

| Flag | Definition |
|---|---|
| DF_BKSP_OK | If set, a single backspace character can move the cursor to the beginning of the overstrike region. If not set, an x-movement cursor command must be sent. (Used only if MTYPE_PAIRED is specified for the character's [**TRANSDATA**](./ns-prntfont-_transdata.md) structure in [**MAPTABLE**](./ns-prntfont-_maptable.md). Otherwise ignored.) |
| DF_NO_BOLD | The device font cannot be bolded using underline simulation. |
| DF_NO_DOUBLE_UNDERLINE | The device font cannot be double-underlined using double-underline simulation. |
| DF_NO_STRIKETHRU | The device font cannot be struck through using strike-through simulation. |
| DF_NOITALIC | The device font cannot be italicized using italic simulation. |
| DF_NOUNDER | The device font cannot be underlined using underline simulation. |
| DF_XM_CR | Unidrv must send a carriage return command after each line of text. |

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

Is an [**INVOC**](./ns-prntfont-_invoc.md) structure containing the printer's font selection command.

### -field UnSelectFont

Is an INVOC structure containing the printer's font deselection command.

### -field wReserved

Not used.

## -remarks

A .ufm (Unidrv Font Metrics) file's UNIDRVINFO structure is accessed by a pointer in the file's [**UNIFM_HDR**](./ns-prntfont-_unifm_hdr.md) structure.

## -see-also

[**INVOC**](./ns-prntfont-_invoc.md)