---
UID: NF:printerextension.IPrintJob.get_PrintedPages
title: IPrintJob::get_PrintedPages (printerextension.h)
description: Gets the number of pages that have been printed.
old-location: print\iprintjob_printedpages.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintJob::get_PrintedPages"]
ms.keywords: IPrintJob interface [Print Devices],PrintedPages property, IPrintJob.PrintedPages, IPrintJob.get_PrintedPages, IPrintJob::PrintedPages, IPrintJob::get_PrintedPages, PrintedPages property [Print Devices], PrintedPages property [Print Devices],IPrintJob interface, get_PrintedPages, print.iprintjob_printedpages, printerextension/IPrintJob::PrintedPages, printerextension/IPrintJob::get_PrintedPages
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - IPrintJob::get_PrintedPages
 - printerextension/IPrintJob::get_PrintedPages
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintJob::get_PrintedPages
---

# IPrintJob::get_PrintedPages


## -description

Gets the number of pages that have been printed.

This property is read-only.

## -parameters

## -remarks

If the <b>PrintedPages</b> and <a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintjob-get_totalpages">IPrintJob::TotalPages</a> properties are both zero, then page delimiting is not supported for the print job.

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintjob">IPrintJob::IPrintJob</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintjob-get_totalpages">TotalPages</a>

