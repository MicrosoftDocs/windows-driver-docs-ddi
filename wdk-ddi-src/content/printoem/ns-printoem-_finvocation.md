---
UID: NS:printoem._FINVOCATION
title: _FINVOCATION (printoem.h)
description: The FINVOCATION structure is used as input to the IPrintOemUni::SendFontCmd method. The structure is defined in printoem.h.
old-location: print\finvocation.htm
tech.root: print
ms.assetid: 958d6f1f-e8e8-43e6-a4d4-73bae4b2be21
ms.date: 04/20/2018
keywords: ["_FINVOCATION structure"]
ms.keywords: "*PFINVOCATION, FINVOCATION, FINVOCATION structure [Print Devices], PFINVOCATION, PFINVOCATION structure pointer [Print Devices], _FINVOCATION, print.finvocation, print_unidrv-pscript_rendering_9937cdea-eacb-457c-af51-d8963ffd59e9.xml, printoem/FINVOCATION, printoem/PFINVOCATION"
f1_keywords:
 - "printoem/FINVOCATION"
 - "FINVOCATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- printoem.h
api_name:
- FINVOCATION
targetos: Windows
req.typenames: FINVOCATION, *PFINVOCATION
---

# _FINVOCATION structure


## -description


The FINVOCATION structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-sendfontcmd">IPrintOemUni::SendFontCmd</a> method. The structure is defined in printoem.h.


## -struct-fields




### -field dwCount

Specifies the Unidrv-supplied length, in bytes, of the command pointed to by <b>pubCommand</b>.


### -field pubCommand

Unidrv-supplied pointer to a string containing the printer's font selection command. The command is obtained from the font's .ufm (Unidrv Font Metrics) file.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-sendfontcmd">IPrintOemUni::SendFontCmd</a>
 

 

