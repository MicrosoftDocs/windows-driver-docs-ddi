---
UID: NS:printoem._GETINFO_GLYPHBITMAP
title: GETINFO_GLYPHBITMAP (printoem.h)
description: The GETINFO_GLYPHBITMAP structure is used as input to the UNIFONTOBJ_GetInfo callback function.
tech.root: print
ms.date: 08/12/2022
keywords: ["GETINFO_GLYPHBITMAP structure"]
ms.keywords: "*PGETINFO_GLYPHBITMAP, GETINFO_GLYPHBITMAP, GETINFO_GLYPHBITMAP structure [Print Devices], PGETINFO_GLYPHBITMAP, PGETINFO_GLYPHBITMAP structure pointer [Print Devices], _GETINFO_GLYPHBITMAP, print.getinfo_glyphbitmap, print_unidrv-pscript_rendering_56355138-13b0-4e8b-8132-f7c017105ab3.xml, printoem/GETINFO_GLYPHBITMAP, printoem/PGETINFO_GLYPHBITMAP"
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
req.typenames: GETINFO_GLYPHBITMAP, *PGETINFO_GLYPHBITMAP
f1_keywords:
 - _GETINFO_GLYPHBITMAP
 - printoem/_GETINFO_GLYPHBITMAP
 - PGETINFO_GLYPHBITMAP
 - printoem/PGETINFO_GLYPHBITMAP
 - GETINFO_GLYPHBITMAP
 - printoem/GETINFO_GLYPHBITMAP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _GETINFO_GLYPHBITMAP
 - PGETINFO_GLYPHBITMAP
 - GETINFO_GLYPHBITMAP
---

## -description

The **GETINFO_GLYPHBITMAP** structure is used as input to the [UNIFONTOBJ_GetInfo](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo) callback function.

## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the **GETINFO_GLYPHBITMAP** structure. Supplied by [UNIFONTOBJ_GetInfo](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo) caller.

### -field hGlyph

Handle to the glyph. See the following Remarks section. Supplied by the [UNIFONTOBJ_GetInfo](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo) caller.

### -field pGlyphData

Pointer to a [GLYPHDATA](/windows/win32/api/winddi/ns-winddi-glyphdata) structure. The structure is filled in by Unidrv's [UNIFONTOBJ_GetInfo](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo) callback function. The pointer is supplied by the *UNIFONTOBJ_GetInfo* caller.

## -remarks

To obtain a glyph bitmap, a rendering plug-in can supply the address of a **GETINFO_GLYPHBITMAP** structure when calling Unidrv's [UNIFONTOBJ_GetInfo](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo) callback function.

The value that a rendering plug-in specifies for the **hGlyph** member must have been previously received as the *hGlyph* parameter to the [IPrintOemUni::DownloadCharGlyph](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-downloadcharglyph) method.

## -see-also

[GLYPHDATA](/windows/win32/api/winddi/ns-winddi-glyphdata)

[IPrintOemUni::DownloadCharGlyph](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-downloadcharglyph)

[UNIFONTOBJ_GetInfo](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo)
