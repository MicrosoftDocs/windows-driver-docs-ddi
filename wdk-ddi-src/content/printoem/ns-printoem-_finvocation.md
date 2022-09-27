---
UID: NS:printoem._FINVOCATION
title: FINVOCATION (printoem.h)
description: The FINVOCATION structure is used as input to the IPrintOemUni::SendFontCmd method. The structure is defined in printoem.h.
tech.root: print
ms.date: 08/12/2022
keywords: ["FINVOCATION structure"]
ms.keywords: "*PFINVOCATION, FINVOCATION, FINVOCATION structure [Print Devices], PFINVOCATION, PFINVOCATION structure pointer [Print Devices], _FINVOCATION, print.finvocation, print_unidrv-pscript_rendering_9937cdea-eacb-457c-af51-d8963ffd59e9.xml, printoem/FINVOCATION, printoem/PFINVOCATION"
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
req.typenames: FINVOCATION, *PFINVOCATION
f1_keywords:
 - _FINVOCATION
 - printoem/_FINVOCATION
 - PFINVOCATION
 - printoem/PFINVOCATION
 - FINVOCATION
 - printoem/FINVOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _FINVOCATION
 - PFINVOCATION
 - FINVOCATION
---

## -description

The **FINVOCATION** structure is used as input to the [IPrintOemUni::SendFontCmd](../prcomoem/nf-prcomoem-iprintoemuni-sendfontcmd.md) method. The structure is defined in printoem.h.

## -struct-fields

### -field dwCount

Specifies the Unidrv-supplied length, in bytes, of the command pointed to by **pubCommand**.

### -field pubCommand

Unidrv-supplied pointer to a string containing the printer's font selection command. The command is obtained from the font's .ufm (Unidrv Font Metrics) file.

## -see-also

[IPrintOemUni::SendFontCmd](../prcomoem/nf-prcomoem-iprintoemuni-sendfontcmd.md)