---
UID: NF:printerextension.IPrintSchemaAsyncOperationEvent.Completed
title: IPrintSchemaAsyncOperationEvent::Completed method
author: windows-driver-content
description: Is called when asynchronous PrintSchema operation that is represented by an IPrintSchemaAsyncOperation context is completed.
old-location: print\iprintschemaasyncoperationevent_completed.htm
old-project: print
ms.assetid: B1599F21-D6DD-497D-9CD8-6C637ABAA33A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintSchemaAsyncOperationEvent::Completed, Completed method [Print Devices], print.iprintschemaasyncoperationevent_completed, Completed, Completed method [Print Devices], IPrintSchemaAsyncOperationEvent interface, IPrintSchemaAsyncOperationEvent interface [Print Devices], Completed method, IPrintSchemaAsyncOperationEvent, printerextension/IPrintSchemaAsyncOperationEvent::Completed
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IPrintSchemaAsyncOperationEvent.Completed
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaAsyncOperationEvent::Completed method


## -description


Is called when asynchronous PrintSchema operation that is represented by an <a href="..\printerextension\nn-printerextension-iprintschemaasyncoperation.md">IPrintSchemaAsyncOperation</a> context is completed.


## -syntax


````
HRESULT Completed(
  [in] IPrintSchemaTicket *pTicket,
  [in] HRESULT            hrOperation
);
````


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

<a href="..\printerextension\nn-printerextension-iprintschemaasyncoperationevent.md">IPrintSchemaAsyncOperationEvent</a>

<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaAsyncOperationEvent::Completed method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

