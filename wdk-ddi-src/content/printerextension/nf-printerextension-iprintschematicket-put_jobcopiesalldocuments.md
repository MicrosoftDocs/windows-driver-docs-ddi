---
UID: NF:printerextension.IPrintSchemaTicket.put_JobCopiesAllDocuments
title: IPrintSchemaTicket::put_JobCopiesAllDocuments
description: Sets the copy count.
old-location: print\iprintschematicket_put_jobcopiesalldocuments.htm
tech.root: print
ms.assetid: DF788C8F-DA60-47F1-83DB-2E1947E41142
ms.date: 04/20/2018
ms.keywords: IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],JobCopiesAllDocuments property, IPrintSchemaTicket.JobCopiesAllDocuments, IPrintSchemaTicket.put_JobCopiesAllDocuments, IPrintSchemaTicket::JobCopiesAllDocuments, IPrintSchemaTicket::put_JobCopiesAllDocuments, JobCopiesAllDocuments property [Print Devices], JobCopiesAllDocuments property [Print Devices],IPrintSchemaTicket interface, print.iprintschematicket_put_jobcopiesalldocuments, printerextension/IPrintSchemaTicket::JobCopiesAllDocuments, printerextension/IPrintSchemaTicket::put_JobCopiesAllDocuments, put_JobCopiesAllDocuments
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
-	IPrintSchemaTicket.JobCopiesAllDocuments
-	IPrintSchemaTicket.put_JobCopiesAllDocuments
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaTicket::put_JobCopiesAllDocuments


## -description


Sets the copy count.

This property is write-only.


## -parameters


## -remarks



Be aware of the fact that the <a href="https://msdn.microsoft.com/5556BD5E-6489-4CCF-8C62-DDA53AD9F368">IPrintSchemaTicket::GetCapabilities</a>  method retrieves a new PrintCapabilities document, which it also caches every time it is invoked. This means that if you use <b>IPrintSchemaTicket::put_JobCopiesAllDocuments</b> or <a href="https://msdn.microsoft.com/DEFA0559-9946-4F4D-B5DC-A0E5E872114A">IPrintSchemaFeature::SelectedOption</a> on PrintTicket, the cached PrintCapabilities document gets corrupted or modified and the cache will be purged. 




## -see-also




<a href="https://msdn.microsoft.com/DEFA0559-9946-4F4D-B5DC-A0E5E872114A">IPrintSchemaFeature::SelectedOption</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>



<a href="https://msdn.microsoft.com/5556BD5E-6489-4CCF-8C62-DDA53AD9F368">IPrintSchemaTicket::GetCapabilities</a>
 

 

