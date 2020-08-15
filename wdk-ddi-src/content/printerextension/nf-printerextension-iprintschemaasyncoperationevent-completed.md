---
UID: NF:printerextension.IPrintSchemaAsyncOperationEvent.Completed
title: IPrintSchemaAsyncOperationEvent::Completed (printerextension.h)
description: Is called when asynchronous PrintSchema operation that is represented by an IPrintSchemaAsyncOperation context is completed.
old-location: print\iprintschemaasyncoperationevent_completed.htm
tech.root: print
ms.assetid: B1599F21-D6DD-497D-9CD8-6C637ABAA33A
ms.date: 04/20/2018
keywords: ["IPrintSchemaAsyncOperationEvent::Completed"]
ms.keywords: Completed, Completed method [Print Devices], Completed method [Print Devices],IPrintSchemaAsyncOperationEvent interface, IPrintSchemaAsyncOperationEvent interface [Print Devices],Completed method, IPrintSchemaAsyncOperationEvent.Completed, IPrintSchemaAsyncOperationEvent::Completed, print.iprintschemaasyncoperationevent_completed, printerextension/IPrintSchemaAsyncOperationEvent::Completed
f1_keywords:
 - "printerextension/IPrintSchemaAsyncOperationEvent.Completed"
 - "IPrintSchemaAsyncOperationEvent.Completed"
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrintSchemaAsyncOperationEvent.Completed
targetos: Windows
req.typenames: 
---

# IPrintSchemaAsyncOperationEvent::Completed


## -description


Is called when asynchronous PrintSchema operation that is represented by an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaasyncoperation">IPrintSchemaAsyncOperation</a> context is completed.


## -parameters




### -param pTicket 
[in]
The print ticket.


### -param hrOperation 
[in]
The result of the completed operation.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



The print ticket passed to the <b>Completed</b> method is the final validated, merged, or committed print ticket.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaasyncoperationevent">IPrintSchemaAsyncOperationEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a>
 

 

