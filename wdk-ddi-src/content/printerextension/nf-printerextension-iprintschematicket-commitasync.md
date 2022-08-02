---
UID: NF:printerextension.IPrintSchemaTicket.CommitAsync
title: IPrintSchemaTicket::CommitAsync (printerextension.h)
description: Gets an asynchronous PrintTicket commit operation context.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintSchemaTicket::CommitAsync"]
ms.keywords: CommitAsync, CommitAsync method [Print Devices], CommitAsync method [Print Devices],IPrintSchemaTicket interface, IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],CommitAsync method, IPrintSchemaTicket.CommitAsync, IPrintSchemaTicket::CommitAsync, print.iprintschematicket_commitasync, printerextension/IPrintSchemaTicket::CommitAsync
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
 - IPrintSchemaTicket::CommitAsync
 - printerextension/IPrintSchemaTicket::CommitAsync
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - printerextension.h
api_name:
 - IPrintSchemaTicket::CommitAsync
---

## -description

Gets an  asynchronous PrintTicket commit operation context.

## -parameters

### -param pPrintTicketCommit [in]

The print ticket to commit.

### -param ppAsyncOperation [out]

The asynchronous commit operation context.

## -returns

This method returns an **HRESULT** value.

## -remarks

To perform the commit operation, call the [IPrintSchemaAsyncOperation::Start](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperation-start) method to validate the given *pPrintTicketCommit* and then apply the validated PrintTicket settings to the current PrintTicket object. When the commit operation is completed or if an error occurs during the commit operation, the [IPrintSchemaAsyncOperationEvent::Completed](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperationevent-completed) event is fired.

## -see-also

[IPrintSchemaAsyncOperation::Start](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperation-start)

[IPrintSchemaAsyncOperationEvent::Completed](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperationevent-completed)

[IPrintSchemaTicket](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket)
