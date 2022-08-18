---
UID: NF:printerextension.IPrintSchemaAsyncOperationEvent.Completed
title: IPrintSchemaAsyncOperationEvent::Completed (printerextension.h)
description: Is called when asynchronous PrintSchema operation that is represented by an IPrintSchemaAsyncOperation context is completed.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintSchemaAsyncOperationEvent::Completed"]
ms.keywords: Completed, Completed method [Print Devices], Completed method [Print Devices],IPrintSchemaAsyncOperationEvent interface, IPrintSchemaAsyncOperationEvent interface [Print Devices],Completed method, IPrintSchemaAsyncOperationEvent.Completed, IPrintSchemaAsyncOperationEvent::Completed, print.iprintschemaasyncoperationevent_completed, printerextension/IPrintSchemaAsyncOperationEvent::Completed
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintSchemaAsyncOperationEvent::Completed
 - printerextension/IPrintSchemaAsyncOperationEvent::Completed
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaAsyncOperationEvent::Completed
---

## -description

Is called when asynchronous PrintSchema operation that is represented by an [IPrintSchemaAsyncOperation](./nn-printerextension-iprintschemaasyncoperation.md) context is completed.

## -parameters

### -param pTicket [in]

The print ticket.

### -param hrOperation [in]

The result of the completed operation.

## -returns

This method returns an **HRESULT** value.

## -remarks

The print ticket passed to the **Completed** method is the final validated, merged, or committed print ticket.

## -see-also

[IPrintSchemaAsyncOperationEvent](./nn-printerextension-iprintschemaasyncoperationevent.md)

[IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md)