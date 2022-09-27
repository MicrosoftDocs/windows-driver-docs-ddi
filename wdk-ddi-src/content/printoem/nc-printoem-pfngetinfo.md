---
UID: NC:printoem.PFNGETINFO
title: PFNGETINFO (printoem.h)
description: The UNIFONTOBJ_GetInfo callback function is provided by the Unidrv driver so that rendering plug-ins can obtain font or glyph information.
tech.root: print
ms.date: 08/11/2022
keywords: ["PFNGETINFO callback function"]
ms.keywords: PFNGETINFO, UNIFONTOBJ_GetInfo, UNIFONTOBJ_GetInfo routine [Print Devices], print.unifontobj_getinfo, print_unidrv-pscript_rendering_7dc55246-beaa-4058-87a3-5438db3368c4.xml, printoem/UNIFONTOBJ_GetInfo
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFNGETINFO
 - printoem/PFNGETINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - PFNGETINFO
---

## -description

The **UNIFONTOBJ_GetInfo** callback function is provided by the Unidrv driver so that rendering plug-ins can obtain font or glyph information.

## -parameters

### -param unnamedParam1

Pointer to the [UNIFONTOBJ](./ns-printoem-_unifontobj.md) structure received by the function that is making the callback to **UNIFONTOBJ_GetInfo**. Supplied by the caller.

### -param unnamedParam2

Specifies the size, in bytes, of the buffer pointed to by *pData*. Supplied by the caller.

### -param unnamedParam3

Pointer to a structure, as indicated in the following table. Supplied by the caller.

| dwInfoID Value | *pData* Structure |
|--|--|
| UFO_GETINFO_FONTOBJ | [GETINFO_FONTOBJ](./ns-printoem-_getinfo_fontobj.md) |
| UFO_GETINFO_GLYPHBITMAP | [GETINFO_GLYPHBITMAP](./ns-printoem-_getinfo_glyphbitmap.md) |
| UFO_GETINFO_GLYPHSTRING | [GETINFO_GLYPHSTRING](./ns-printoem-_getinfo_glyphstring.md) |
| UFO_GETINFO_GLYPHWIDTH | [GETINFO_GLYPHWIDTH](./ns-printoem-_getinfo_glyphwidth.md) |
| UFO_GETINFO_MEMORY | [GETINFO_MEMORY](./ns-printoem-_getinfo_memory.md) |
| UFO_GETINFO_STDVARIABLE | [GETINFO_STDVAR](./ns-printoem-_getinfo_stdvar.md) |

For more information, see the table in the **Remarks** section.

### -param unnamedParam4

Specifies the type of structure pointed to by *pData*. Supplied by the caller. For more information, see the table in the **Remarks** section.

### -param unnamedParam5

Pointer to a location that receives the minimum buffer size, in bytes, required to contain the structure identified by *dwInfoID*. Supplied by the caller.

## -returns

Returns a **BOOL** value. If the operation succeeds, the function returns **TRUE**. Otherwise it returns **FALSE**.

## -remarks

The **UNIFONTOBJ_GetInfo** callback function allows a [rendering plug-in](/windows-hardware/drivers/print/rendering-plug-ins) to call back into Unidrv to obtain font or glyph information from GDI, needed for handling [customized font management](/windows-hardware/drivers/print/customized-font-management) operations.

A rendering plug-in receives the **UNIFONTOBJ_GetInfo** function's address in the [UNIFONTOBJ](./ns-printoem-_unifontobj.md) structure that is passed to the font customization methods.

The type of information returned by the function is dependent on the input arguments. The caller supplies values for *dwInfoID*, *pData*, and *dwDataSize* to indicate the type of information wanted. The following table summarizes the types of information returned. For more information, see the structure descriptions.

| *pData* Structure | Returned Information |
|--|--|
| [GETINFO_FONTOBJ](./ns-printoem-_getinfo_fontobj.md) | A FONTOBJ structure describing the current font. |
| [GETINFO_GLYPHBITMAP](./ns-printoem-_getinfo_glyphbitmap.md) | A single glyph bitmap. |
| [GETINFO_GLYPHSTRING](./ns-printoem-_getinfo_glyphstring.md) | An array of glyph specifiers in a specified format. |
| [GETINFO_GLYPHWIDTH](./ns-printoem-_getinfo_glyphwidth.md) | Total width of a set of glyphs. |
| [GETINFO_MEMORY](./ns-printoem-_getinfo_memory.md) | Amount of available printer memory remaining. |
| [GETINFO_STDVAR](./ns-printoem-_getinfo_stdvar.md) | The current value for one or more of Unidrv's [standard variables](/windows-hardware/drivers/print/standard-variables). |

If the buffer described by *pData* and *dwDataSize* is too small to receive the structure indicated by *dwInfoID*, the function loads the required buffer size into the location pointed by *pcbNeeded* and returns **FALSE**.