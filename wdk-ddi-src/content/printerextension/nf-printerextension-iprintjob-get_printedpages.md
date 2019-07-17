---
UID: NF:printerextension.IPrintJob.get_PrintedPages
title: IPrintJob::get_PrintedPages (printerextension.h)
description: Gets the number of pages that have been printed.
old-location: print\iprintjob_printedpages.htm
tech.root: print
ms.assetid: 37F09500-1EDB-459D-8845-789734081B0C
ms.date: 04/20/2018
ms.keywords: IPrintJob interface [Print Devices],PrintedPages property, IPrintJob.PrintedPages, IPrintJob.get_PrintedPages, IPrintJob::PrintedPages, IPrintJob::get_PrintedPages, PrintedPages property [Print Devices], PrintedPages property [Print Devices],IPrintJob interface, get_PrintedPages, print.iprintjob_printedpages, printerextension/IPrintJob::PrintedPages, printerextension/IPrintJob::get_PrintedPages
ms.topic: method
f1_keywords:
 - "printerextension/IPrintJob.PrintedPages"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrintJob.PrintedPages
- IPrintJob.get_PrintedPages
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintJob::get_PrintedPages


## -description


Gets the number of pages that have been printed.

This property is read-only.


## -parameters


## -remarks



If the <b>PrintedPages</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintjob-get_totalpages">IPrintJob::TotalPages</a> properties are both zero, then page delimiting is not supported for the print job.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintjob">IPrintJob::IPrintJob</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintjob-get_totalpages">TotalPages</a>
 

 

