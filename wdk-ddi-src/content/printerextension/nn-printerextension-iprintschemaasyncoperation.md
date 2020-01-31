---
UID: NN:printerextension.IPrintSchemaAsyncOperation
title: IPrintSchemaAsyncOperation (printerextension.h)
description: Represents an asynchronous operation context for validation, merge or commit operations.
old-location: print\iprintschemaasyncoperation_interface.htm
tech.root: print
ms.assetid: CEA80412-4B19-493B-A85E-625915D77CA5
ms.date: 04/20/2018
ms.keywords: IPrintSchemaAsyncOperation, IPrintSchemaAsyncOperation interface [Print Devices], IPrintSchemaAsyncOperation interface [Print Devices],described, print.iprintschemaasyncoperation_interface, printerextension/IPrintSchemaAsyncOperation
f1_keywords:
 - "printerextension/IPrintSchemaAsyncOperation"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrintSchemaAsyncOperation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaAsyncOperation interface

## -description

Represents an asynchronous operation context for validation, merge or commit operations.

## -inheritance

## -remarks

Any event sink that implements [IPrintSchemaAsyncOperationEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaasyncoperationevent) is connected to the associated event source, **IPrintSchemaAsyncOperation**, via the [IConnectionPoint](https://docs.microsoft.com/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint) mechanism. You must retrieve a pointer to the **IConnectionPoint** interface by invoking **QueryInterface** on the **IPrinterQueue** object.

> [!NOTE]
> It is mandatory to implement **IDispatch::Invoke** on the event sink that implements **IPrinterQueueEvent**, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the **IDispatch** interface.

## -see-also

[IConnectionPoint](https://docs.microsoft.com/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint)

[IPrintSchemaAsyncOperationEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaasyncoperationevent)
