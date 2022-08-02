---
UID: NF:printerextension.IPrintSchemaTicket.ValidateAsync
title: IPrintSchemaTicket::ValidateAsync (printerextension.h)
description: Gets an asynchronous PrintTicket validation operation context.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintSchemaTicket::ValidateAsync"]
ms.keywords: IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],ValidateAsync method, IPrintSchemaTicket.ValidateAsync, IPrintSchemaTicket::ValidateAsync, ValidateAsync, ValidateAsync method [Print Devices], ValidateAsync method [Print Devices],IPrintSchemaTicket interface, print.iprintschematicket_validateasync, printerextension/IPrintSchemaTicket::ValidateAsync
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
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
 - IPrintSchemaTicket::ValidateAsync
 - printerextension/IPrintSchemaTicket::ValidateAsync
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - printerextension.h
api_name:
 - IPrintSchemaTicket::ValidateAsync
---

## -description

Gets an asynchronous **PrintTicket** validation operation context.

## -parameters

### -param ppAsyncOperation [out]

The asynchronous validation operation context.

## -returns

This method returns an **HRESULT** value.

## -remarks

 To perform the validation operation, call the [IPrintSchemaAsyncOperation::Start](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperation-start) method to validate the settings of the current PrintTicket object and to pass the resulting **PrintTicket** to the [IPrintSchemaAsyncOperationEvent::Completed](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperationevent-completed) event. When the validation operation is completed, or if an error occurs during the validation operation, the **IPrintSchemaAsyncOperationEvent::Completed** event is fired. This method will not change the settings of the current **PrintTicket** object.

## -see-also

[IPrintSchemaAsyncOperation](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaasyncoperation)

[IPrintSchemaAsyncOperation::Start](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperation-start)

[IPrintSchemaAsyncOperationEvent::Completed](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperationevent-completed)

[IPrintSchemaTicket](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket)
