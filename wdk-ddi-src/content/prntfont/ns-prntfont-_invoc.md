---
UID: NS:prntfont._INVOC
title: _INVOC (prntfont.h)
description: The INVOC structure is used for describing printer command strings in Unidrv font metrics files (.ufm files) and glyph translation table files (.gtt files).
old-location: print\invoc.htm
tech.root: print
ms.assetid: 5eeaa7f7-dc99-4cf7-846c-801954cc9040
ms.date: 04/20/2018
keywords: ["INVOC structure"]
ms.keywords: "*PINVOC, INVOC, INVOC structure [Print Devices], PINVOC, PINVOC structure pointer [Print Devices], _INVOC, print.invoc, print_unidrv-pscript_fonts_1c5bebe8-a2ca-4049-bcce-defd8622761b.xml, prntfont/INVOC, prntfont/PINVOC"
f1_keywords:
 - "prntfont/INVOC"
 - "INVOC"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- prntfont.h
api_name:
- INVOC
targetos: Windows
req.typenames: INVOC, *PINVOC
---

# _INVOC structure


## -description


The INVOC structure is used for describing printer command strings in <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-management">Unidrv font metrics files</a> (.ufm files) and <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-management">glyph translation table files</a> (.gtt files).


## -struct-fields




### -field dwCount

Specifies the number of characters in the command.


### -field loOffset

Indicates one of the following:





##### ufm files:

Specifies the byte offset from the beginning of the .ufm file's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_unidrvinfo">UNIDRVINFO</a> structure to beginning of the command string.



##### gtt files:

Specifies the byte offset from the beginning of the .gtt file's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_uni_codepageinfo">UNI_CODEPAGEINFO</a> structure to beginning of the command string.


## -remarks



INVOC structures are used within <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_unidrvinfo">UNIDRVINFO</a> structures.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_unidrvinfo">UNIDRVINFO</a>
 

 

