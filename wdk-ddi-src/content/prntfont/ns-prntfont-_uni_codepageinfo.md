---
UID: NS:prntfont._UNI_CODEPAGEINFO
title: _UNI_CODEPAGEINFO (prntfont.h)
description: The UNI_CODEPAGEINFO structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\uni_codepageinfo.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["UNI_CODEPAGEINFO structure"]
ms.keywords: "*PUNI_CODEPAGEINFO, PUNI_CODEPAGEINFO, PUNI_CODEPAGEINFO structure pointer [Print Devices], UNI_CODEPAGEINFO, UNI_CODEPAGEINFO structure [Print Devices], _UNI_CODEPAGEINFO, print.uni_codepageinfo, print_unidrv-pscript_fonts_63611a4f-c59c-4fee-a8f3-c1391ff02afd.xml, prntfont/PUNI_CODEPAGEINFO, prntfont/UNI_CODEPAGEINFO"
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
req.typenames: UNI_CODEPAGEINFO, *PUNI_CODEPAGEINFO
f1_keywords:
 - _UNI_CODEPAGEINFO
 - prntfont/_UNI_CODEPAGEINFO
 - PUNI_CODEPAGEINFO
 - prntfont/PUNI_CODEPAGEINFO
 - UNI_CODEPAGEINFO
 - prntfont/UNI_CODEPAGEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - prntfont.h
api_name:
 - UNI_CODEPAGEINFO
---

# _UNI_CODEPAGEINFO structure


## -description

The UNI_CODEPAGEINFO structure is one of the structures used to define the contents of <a href="/windows-hardware/drivers/print/customized-font-management">glyph translation table files</a> (.gtt files).

## -struct-fields

### -field dwCodePage

Identifies a Windows code page.

### -field SelectSymbolSet

Is an <a href="/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_invoc">INVOC</a> structure containing the printer command to select the code page's symbol set.

### -field UnSelectSymbolSet

Is an <a href="/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_invoc">INVOC</a> structure containing the printer command to deselect the code page's symbol set.

## -see-also

<a href="/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_invoc">INVOC</a>
