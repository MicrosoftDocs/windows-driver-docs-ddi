---
UID: NS:prntfont._KERNDATA
title: _KERNDATA (prntfont.h)
description: The KERNDATA structure is used for describing printer kerning pairs.
old-location: print\kerndata.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["KERNDATA structure"]
ms.keywords: "*PKERNDATA, KERNDATA, KERNDATA structure [Print Devices], PKERNDATA, PKERNDATA structure pointer [Print Devices], _KERNDATA, print.kerndata, print_unidrv-pscript_fonts_9ddb2b69-839c-496a-b252-691570ee03cb.xml, prntfont/KERNDATA, prntfont/PKERNDATA"
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
req.typenames: KERNDATA, *PKERNDATA
f1_keywords:
 - _KERNDATA
 - prntfont/_KERNDATA
 - PKERNDATA
 - prntfont/PKERNDATA
 - KERNDATA
 - prntfont/KERNDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - prntfont.h
api_name:
 - KERNDATA
---

# _KERNDATA structure


## -description

The KERNDATA structure is used for describing printer kerning pairs.

## -struct-fields

### -field dwSize

Specifies the size, in bytes, of KERNDATA structure, including the <b>KernPair</b> array.

### -field dwKernPairNum

Specifies the number of elements in the <b>KernPair</b> array.

### -field KernPair

Is an array of <a href="/windows/win32/api/winddi/ns-winddi-fd_kerningpair">FD_KERNINGPAIR</a> structures.

## -remarks

A .ufm file's KERNDATA structures are accessed by a pointer in the file's <a href="/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_unifm_hdr">UNIFM_HDR</a> structure.

## -see-also

<a href="/windows/win32/api/winddi/ns-winddi-fd_kerningpair">FD_KERNINGPAIR</a>



<a href="/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_unifm_hdr">UNIFM_HDR</a>
