---
UID: NF:printerextension.IPrintJob.get_PrintedPages
title: IPrintJob::get_PrintedPages
author: windows-driver-content
description: Gets the number of pages that have been printed.
old-location: print\iprintjob_printedpages.htm
tech.root: print
ms.assetid: 37F09500-1EDB-459D-8845-789734081B0C
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintJob interface [Print Devices],PrintedPages property, IPrintJob.PrintedPages, IPrintJob.get_PrintedPages, IPrintJob::PrintedPages, IPrintJob::get_PrintedPages, PrintedPages property [Print Devices], PrintedPages property [Print Devices],IPrintJob interface, get_PrintedPages, print.iprintjob_printedpages, printerextension/IPrintJob::PrintedPages, printerextension/IPrintJob::get_PrintedPages
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintJob.PrintedPages
-	IPrintJob.get_PrintedPages
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



If the <b>PrintedPages</b> and <a href="https://msdn.microsoft.com/1035337F-2EDD-4538-AF39-3828B6DE424B">IPrintJob::TotalPages</a> properties are both zero, then page delimiting is not supported for the print job.




## -see-also




<a href="https://msdn.microsoft.com/068E53EC-26B8-48E7-A605-081709C94043">IPrintJob::IPrintJob</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265411">TotalPages</a>
 

 

