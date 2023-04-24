---
UID: NS:printoem._GETINFO_STDVAR
title: GETINFO_STDVAR (printoem.h)
description: The GETINFO_STDVAR structure is used as input to the UNIFONTOBJ_GetInfo callback function.
tech.root: print
ms.date: 08/12/2022
keywords: ["GETINFO_STDVAR structure"]
ms.keywords: "*PGETINFO_STDVAR, GETINFO_STDVAR, GETINFO_STDVAR structure [Print Devices], PGETINFO_STDVAR, PGETINFO_STDVAR structure pointer [Print Devices], _GETINFO_STDVAR, print.getinfo_stdvar, print_unidrv-pscript_rendering_3a08d48b-215f-4acc-89ef-849a2b826ce7.xml, printoem/GETINFO_STDVAR, printoem/PGETINFO_STDVAR"
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
targetos: Windows
req.typenames: GETINFO_STDVAR, *PGETINFO_STDVAR
f1_keywords:
 - _GETINFO_STDVAR
 - printoem/_GETINFO_STDVAR
 - PGETINFO_STDVAR
 - printoem/PGETINFO_STDVAR
 - GETINFO_STDVAR
 - printoem/GETINFO_STDVAR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _GETINFO_STDVAR
 - PGETINFO_STDVAR
 - GETINFO_STDVAR
---

## -description

The **GETINFO_STDVAR** structure is used as input to the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function.

## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the **GETINFO_STDVAR** structure. Supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field dwNumOfVariable

Defines the **DWORD** member **dwNumOfVariable**.

### -field dwStdVarID

Defines the **DWORD** member **dwStdVarID**.

### -field lStdVariable

Defines the **LONG** member **lStdVariable**.

### -field StdVar

An array specifying standard variable indexes and values. Each array element contains two members: a **dwStdVarID** member and an **lStdVariable** member.

#### dwStdVarID

Specifies the [standard variables](/windows-hardware/drivers/print/standard-variables) for which a value should be returned. Supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller. Valid values are contained in the following table.

| Identifier                   | Standard Variable     |
|------------------------------|-----------------------|
| FNT_INFO_CURRENTFONTID       | CurrentFontID       |
| FNT_INFO_FONTBOLD            | FontBold            |
| FNT_INFO_FONTHEIGHT          | FontHeight          |
| FNT_INFO_FONTITALIC          | FontItalic          |
| FNT_INFO_FONTMAXWIDTH        | FontMaxWidth        |
| FNT_INFO_FONTSTRIKETHRU      | FontStrikeThru      |
| FNT_INFO_FONTUNDERLINE       | FontUnderline       |
| FNT_INFO_FONTWIDTH           | FontWidth           |
| FNT_INFO_GRAYPERCENTAGE      | GrayPercentage      |
| FNT_INFO_NEXTFONTID          | NextFontID          |
| FNT_INFO_NEXTGLYPH           | NextGlyph           |
| FNT_INFO_PRINTDIRINCCDEGREES | PrintDirInCCDegrees |
| FNT_INFO_TEXTXRES            | TextXRes            |
| FNT_INFO_TEXTYRES            | TextYRes            |

Supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

#### lStdVariable

Specifies the current value of the specified standard variable. Supplied by Unidrv's [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function.

## -remarks

To obtain the current value for one or more of Unidrv's standard variables, a rendering plug-in can supply the address of a GETINFO_STDVAR structure when calling Unidrv's [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function.

For more information about [standard variables](/windows-hardware/drivers/print/standard-variables), see [Microsoft Universal Printer Driver](/windows-hardware/drivers/print/microsoft-universal-printer-driver).

## -see-also

[UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md)