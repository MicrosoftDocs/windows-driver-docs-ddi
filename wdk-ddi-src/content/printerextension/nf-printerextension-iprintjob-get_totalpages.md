---
UID: NF:printerextension.IPrintJob.get_TotalPages
title: IPrintJob::get_TotalPages method
author: windows-driver-content
description: Gets the total number of pages that the document contains.
old-location: print\iprintjob_totalpages.htm
old-project: print
ms.assetid: 1035337F-2EDD-4538-AF39-3828B6DE424B
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: get_TotalPages, IPrintJob.TotalPages, print.iprintjob_totalpages, printerextension/IPrintJob::TotalPages, IPrintJob, IPrintJob::get_TotalPages, printerextension/IPrintJob::get_TotalPages, IPrintJob interface [Print Devices], TotalPages property, TotalPages property [Print Devices], TotalPages property [Print Devices], IPrintJob interface
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
-	IPrintJob.TotalPages
-	IPrintJob.get_TotalPages
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintJob::get_TotalPages method


## -description


Gets the total number of pages that the document contains.

This property is read-only.


## -syntax


````
HRESULT get_TotalPages(
  [out, retval] ULONG *pulPages
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintJob::TotalPages property%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

