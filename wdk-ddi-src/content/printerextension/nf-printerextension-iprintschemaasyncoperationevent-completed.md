---
UID: NF:printerextension.IPrintSchemaAsyncOperationEvent.Completed
title: IPrintSchemaAsyncOperationEvent::Completed
description: Is called when asynchronous PrintSchema operation that is represented by an IPrintSchemaAsyncOperation context is completed.
old-location: print\iprintschemaasyncoperationevent_completed.htm
tech.root: print
ms.assetid: B1599F21-D6DD-497D-9CD8-6C637ABAA33A
ms.date: 04/20/2018
ms.keywords: Completed, Completed method [Print Devices], Completed method [Print Devices],IPrintSchemaAsyncOperationEvent interface, IPrintSchemaAsyncOperationEvent interface [Print Devices],Completed method, IPrintSchemaAsyncOperationEvent.Completed, IPrintSchemaAsyncOperationEvent::Completed, print.iprintschemaasyncoperationevent_completed, printerextension/IPrintSchemaAsyncOperationEvent::Completed
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaAsyncOperationEvent.Completed
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaAsyncOperationEvent::Completed


## -description


Is called when asynchronous PrintSchema operation that is represented by an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451224">IPrintSchemaAsyncOperation</a> context is completed.


## -parameters




### -param pTicket [in]

The print ticket.


### -param hrOperation [in]

The result of the completed operation.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



The print ticket passed to the <b>Completed</b> method is the final validated, merged, or committed print ticket.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451211">IPrintSchemaAsyncOperationEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>
 

 

