---
UID: NF:printerextension.IPrintSchemaTicket.get_JobCopiesAllDocuments
title: IPrintSchemaTicket::get_JobCopiesAllDocuments method
author: windows-driver-content
description: Gets the copy count.
old-location: print\iprintschematicket_jobcopiesalldocuments.htm
old-project: print
ms.assetid: 592753D2-9121-4935-B966-390B3E7778C7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: print.iprintschematicket_jobcopiesalldocuments, printerextension/IPrintSchemaTicket::JobCopiesAllDocuments, JobCopiesAllDocuments property [Print Devices], IPrintSchemaTicket.JobCopiesAllDocuments, IPrintSchemaTicket, get_JobCopiesAllDocuments, JobCopiesAllDocuments property [Print Devices], IPrintSchemaTicket interface, printerextension/IPrintSchemaTicket::get_JobCopiesAllDocuments, IPrintSchemaTicket::get_JobCopiesAllDocuments, IPrintSchemaTicket interface [Print Devices], JobCopiesAllDocuments property
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	IPrintSchemaTicket.JobCopiesAllDocuments
-	IPrintSchemaTicket.get_JobCopiesAllDocuments
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaTicket::get_JobCopiesAllDocuments method


## -description


Gets the copy count.

This property is read-only.


## -syntax


````
HRESULT get_JobCopiesAllDocuments(
  [out, retval] ULONG *pulJobCopiesAllDocuments
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaTicket::JobCopiesAllDocuments property%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

