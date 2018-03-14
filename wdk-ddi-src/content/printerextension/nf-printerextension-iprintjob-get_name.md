---
UID: NF:printerextension.IPrintJob.get_Name
title: IPrintJob::get_Name method
author: windows-driver-content
description: Gets the name of the printer for this print queue.
old-location: print\iprinterqueue_name.htm
old-project: print
ms.assetid: BB8CAEFC-3CD5-46EA-89A8-FAF38063A185
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintJob, IPrintJob::get_Name, IPrinterQueue interface [Print Devices], Name property, IPrinterQueue.Name, IPrinterQueue::get_Name, Name property [Print Devices], Name property [Print Devices], IPrinterQueue interface, get_Name, get_Name,IPrintJob.get_Name, print.iprinterqueue_name, printerextension/IPrinterQueue::Name, printerextension/IPrinterQueue::get_Name
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
-	IPrinterQueue.Name
-	IPrinterQueue.get_Name
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintJob::get_Name method


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



 

 


