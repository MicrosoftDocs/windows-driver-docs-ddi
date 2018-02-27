---
UID: NF:printerextension.IPrintJob.get_PrintedPages
title: IPrintJob::get_PrintedPages method
author: windows-driver-content
description: Gets the number of pages that have been printed.
old-location: print\iprintjob_printedpages.htm
old-project: print
ms.assetid: 37F09500-1EDB-459D-8845-789734081B0C
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintJob, IPrintJob interface [Print Devices], PrintedPages property, IPrintJob.PrintedPages, IPrintJob::get_PrintedPages, PrintedPages property [Print Devices], PrintedPages property [Print Devices], IPrintJob interface, get_PrintedPages, get_PrintedPages,IPrintJob.get_PrintedPages, print.iprintjob_printedpages, printerextension/IPrintJob::PrintedPages, printerextension/IPrintJob::get_PrintedPages
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintJob.PrintedPages
-	IPrintJob.get_PrintedPages
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintJob::get_PrintedPages method


## -description


Gets the number of pages that have been printed.

This property is read-only.


## -syntax


````
HRESULT get_PrintedPages(
  [out, retval] ULONG *pulPages
);
````


## -parameters


## -remarks



If the <b>PrintedPages</b> and <a href="https://msdn.microsoft.com/1035337F-2EDD-4538-AF39-3828B6DE424B">IPrintJob::TotalPages</a> properties are both zero, then page delimiting is not supported for the print job.




## -see-also

<a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob::IPrintJob</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265411">TotalPages</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintJob::PrintedPages property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

