---
UID: NS:printoem._GETINFO_GLYPHSTRING
title: GETINFO_GLYPHSTRING (printoem.h)
description: The GETINFO_GLYPHSTRING structure is used as input to the UNIFONTOBJ_GetInfo callback function.
tech.root: print
ms.date: 08/12/2022
keywords: ["GETINFO_GLYPHSTRING structure"]
ms.keywords: "*PGETINFO_GLYPHSTRING, GETINFO_GLYPHSTRING, GETINFO_GLYPHSTRING structure [Print Devices], PGETINFO_GLYPHSTRING, PGETINFO_GLYPHSTRING structure pointer [Print Devices], _GETINFO_GLYPHSTRING, print.getinfo_glyphstring, print_unidrv-pscript_rendering_5b2786d4-2633-4abe-8eaf-23e7100f7ba3.xml, printoem/GETINFO_GLYPHSTRING, printoem/PGETINFO_GLYPHSTRING"
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
req.typenames: GETINFO_GLYPHSTRING, *PGETINFO_GLYPHSTRING
f1_keywords:
 - _GETINFO_GLYPHSTRING
 - printoem/_GETINFO_GLYPHSTRING
 - PGETINFO_GLYPHSTRING
 - printoem/PGETINFO_GLYPHSTRING
 - GETINFO_GLYPHSTRING
 - printoem/GETINFO_GLYPHSTRING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _GETINFO_GLYPHSTRING
 - PGETINFO_GLYPHSTRING
 - GETINFO_GLYPHSTRING
---

## -description

The **GETINFO_GLYPHSTRING** structure is used as input to the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function.

## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the **GETINFO_GLYPHSTRING** structure. This value is supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field dwCount

Specifies the number of elements in the arrays pointed to by **pGlyphIn** and **pGlyphOut**. This value is supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field dwTypeIn

Specifies the type of glyph specifier array pointed to by **pGlyphIn**. Valid values are as follows:

| Value | Definition |
|--|--|
| TYPE_GLYPHHANDLE | T**pGlyphIn** array elements are of type HGLYPH, or handle to a device font glyph. For this value of **dwTypeIn**, valid values for **dwTypeOut** are either TYPE_UNICODE or TYPE_TRANSDATA. |
| TYPE_GLYPHID | The **pGlyphIn** array elements are of type DWORD, and contain glyph identifiers for downloaded TrueType font glyphs. For this value of **dwTypeIn**, valid values for **dwTypeOut** are either TYPE_UNICODE or TYPE_GLYPHHANDLE. |

Supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field pGlyphIn

Pointer to an array of glyph specifiers. The array element type is indicated by **dwTypeIn**. This value is supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field dwTypeOut

Specifies the type of glyph specifier array pointed to by **pGlyphOut**. Valid values are as follows:

| Value | Definition |
|--|--|
| TYPE_GLYPHHANDLE | The **pGlyphOut** array elements are of type HGLYPH, or handle to a device font glyph. This value is valid only when **dwTypeIn** has been set to TYPE_GLYPHID. |
| TYPE_TRANSDATA | The **pGlyphOut** array elements are of type [TRANSDATA](../prntfont/ns-prntfont-_transdata.md). This value is valid only when **dwTypeIn** has been set to TYPE_GLYPHHANDLE. |
| TYPE_UNICODE | The *pGlyph* array elements are of type WCHAR. This value is valid when **dwTypeIn** has been set to either TYPE_GLYPHHANDLE or TYPE_GLYPHID. |

Supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field pGlyphOut

Caller-supplied pointer to an empty array of glyph specifiers. The array is filled in by Unidrv's [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function. The array element type is indicated by **dwTypeOut**. This pointer is supplied by the UNIFONTOBJ_GetInfo caller.

### -field dwGlyphOutSize

Specifies the size, in bytes, of the buffer pointed to by **pGlyphOut**. This member is used only when **dwTypeIn** has been set to TYPE_GLYPHHANDLE and **dwTypeOut** has been set to TYPE_TRANSDATA. See the following Remarks section for more information.

## -remarks

To convert an array of glyph specifiers from one type to another, a rendering plug-in can supply the address of a GETINFO_GLYPHSTRING structure when calling Unidrv's [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function.

If the conversion is from TYPE_GLYPHHANDLE to TYPE_TRANSDATA, [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) must be called twice.

- Before the first call to [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md), the rendering plug-in fills in the **dwSize**, **dwCount**, **dwTypeIn**, and **pGlyphIn** members and sets **dwGlyphOutSize** member to zero.

  After [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) returns, the **dwGlyphOutSize** member contains the size, in bytes, of the buffer needed to store the converted string.

- The plug-in allocates a block of memory of the size received in the **dwGlyphOutSize** member, sets the **pGlyphOut** member to point to this memory block, and calls [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) once more. UNIDRV then converts the string from TYPE_GLYPHHANDLE to TYPE_TRANSDATA.

The values that a rendering plug-in specifies for the **dwTypeIn**and **pGlyphIn** members typically are those that were previously received as the **dwType**and *pGlyph* parameters to the [IPrintOemUni::OutputCharStr](../prcomoem/nf-prcomoem-iprintoemuni-outputcharstr.md) method.

## -see-also

[IPrintOemUni::OutputCharStr](../prcomoem/nf-prcomoem-iprintoemuni-outputcharstr.md)

[UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md)