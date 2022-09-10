---
UID: NS:printoem._GETINFO_GLYPHWIDTH
title: GETINFO_GLYPHWIDTH (printoem.h)
description: The GETINFO_GLYPHWIDTH structure is used as input to the UNIFONTOBJ_GetInfo callback function.
tech.root: print
ms.date: 08/12/2022
keywords: ["GETINFO_GLYPHWIDTH structure"]
ms.keywords: "*PGETINFO_GLYPHWIDTH, GETINFO_GLYPHWIDTH, GETINFO_GLYPHWIDTH structure [Print Devices], PGETINFO_GLYPHWIDTH, PGETINFO_GLYPHWIDTH structure pointer [Print Devices], _GETINFO_GLYPHWIDTH, print.getinfo_glyphwidth, print_unidrv-pscript_rendering_d4e07803-7342-4550-90fd-1ee8669934f0.xml, printoem/GETINFO_GLYPHWIDTH, printoem/PGETINFO_GLYPHWIDTH"
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
req.typenames: GETINFO_GLYPHWIDTH, *PGETINFO_GLYPHWIDTH
f1_keywords:
 - _GETINFO_GLYPHWIDTH
 - printoem/_GETINFO_GLYPHWIDTH
 - PGETINFO_GLYPHWIDTH
 - printoem/PGETINFO_GLYPHWIDTH
 - GETINFO_GLYPHWIDTH
 - printoem/GETINFO_GLYPHWIDTH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _GETINFO_GLYPHWIDTH
 - PGETINFO_GLYPHWIDTH
 - GETINFO_GLYPHWIDTH
---

## -description

The **GETINFO_GLYPHWIDTH** structure is used as input to the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function.

## -struct-fields

### -field dwSize

Size, in bytes, of the **GETINFO_GLYPHWIDTH** structure. Supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field dwType

Specifies the type of the glyph specifier array pointed to by **pGlyph**. Valid values are:

- TYPE_GLYPHHANDLE

- TYPE_GLYPHID

Supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field dwCount

Specifies the number of elements in the array pointed to by **pGlyph**. Supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field pGlyph

Pointer to an array of glyph specifiers. The array element type is indicated by **dwType**. Supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field plWidth

Pointer to a location into which Unidrv's [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function places the width value. The pointer is supplied by the UNIFONTOBJ_GetInfo caller.

## -remarks

To obtain the width of a set of glyphs, a rendering plug-in can supply the address of a GETINFO_GLYPHWIDTH structure when calling Unidrv's [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function. The callback function calculates the total width of all the glyphs described by the input array, and places the calculated value in the location pointed to by **plWidth**.

## -see-also

[UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md)