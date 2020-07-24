---
UID: NS:prntfont._WIDTHTABLE
title: _WIDTHTABLE (prntfont.h)
description: The WIDTHTABLE structure is used to define the contents of Unidrv font metrics files (.ufm files).
old-location: print\widthtable.htm
tech.root: print
ms.assetid: 6c7b35a2-f9fd-41a9-a353-ec8b78259bf0
ms.date: 04/20/2018
keywords: ["_WIDTHTABLE structure"]
ms.keywords: "*PWIDTHTABLE, PWIDTHTABLE, PWIDTHTABLE structure pointer [Print Devices], WIDTHTABLE, WIDTHTABLE structure [Print Devices], _WIDTHTABLE, print.widthtable, print_unidrv-pscript_fonts_a09173f6-51f7-4523-8270-a0406999f776.xml, prntfont/PWIDTHTABLE, prntfont/WIDTHTABLE"
f1_keywords:
 - "prntfont/WIDTHTABLE"
 - "WIDTHTABLE"
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
- WIDTHTABLE
targetos: Windows
req.typenames: WIDTHTABLE, *PWIDTHTABLE
---

# _WIDTHTABLE structure


## -description


The WIDTHTABLE structure is used to define the contents of <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-management">Unidrv font metrics files</a> (.ufm files).


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the WIDTHTABLE structure, including the <b>WidthRun</b> array.


### -field dwRunNum

Specifies the number of elements in the <b>WidthRun</b> array.


### -field WidthRun

Is an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_widthrun">WIDTHRUN</a> structures.


## -remarks



A .ufm file's WIDTHTABLE structure, which describes character widths, is accessed by a pointer in the file's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_unifm_hdr">UNIFM_HDR</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_unifm_hdr">UNIFM_HDR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_widthrun">WIDTHRUN</a>
 

 

