---
UID: NF:printerextension.IPrintSchemaElement.get_Name
title: IPrintSchemaElement::get_Name method
author: windows-driver-content
description: Gets the name of the printer for this print queue.
old-location: print\iprinterqueue_name.htm
old-project: print
ms.assetid: BB8CAEFC-3CD5-46EA-89A8-FAF38063A185
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, E, I, IPrintJob, IPrintJob::get_Name, IPrintSchemaElement, IPrintSchemaElement::get_Name, IPrinterQueue, IPrinterQueue interface [Print Devices], Name property, IPrinterQueue.Name, IPrinterQueue::get_Name, N, Name property [Print Devices], Name property [Print Devices], IPrinterQueue interface, P, S, _, a, c, e, g, get_Name, get_Name,IPrintJob.get_Name, get_Name,IPrintSchemaElement.get_Name, get_Name,IPrinterQueue.get_Name, h, i, l, m, n, print.iprinterqueue_name, printerextension/IPrinterQueue::Name, printerextension/IPrinterQueue::get_Name, r, t"
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
-	IPrinterQueue.Name
-	IPrinterQueue.get_Name
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaElement::get_Name method


## -description


Gets the name of the printer for this print queue.

This property is read-only.


## -syntax


````
HRESULT get_Name(
  [out, retval] BSTR *pbstrName
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueue::Name property%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

