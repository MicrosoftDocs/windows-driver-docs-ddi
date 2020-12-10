---
UID: NN:printerextension.IPrintSchemaAsyncOperationEvent
title: IPrintSchemaAsyncOperationEvent (printerextension.h)
description: Exposes a validation, merge, or commit completion event delegate.
old-location: print\iprintschemaasyncoperationevent_interface.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintSchemaAsyncOperationEvent interface"]
ms.keywords: IPrintSchemaAsyncOperationEvent, IPrintSchemaAsyncOperationEvent interface [Print Devices], IPrintSchemaAsyncOperationEvent interface [Print Devices],described, print.iprintschemaasyncoperationevent_interface, printerextension/IPrintSchemaAsyncOperationEvent
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintSchemaAsyncOperationEvent
 - printerextension/IPrintSchemaAsyncOperationEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaAsyncOperationEvent
---

# IPrintSchemaAsyncOperationEvent interface


## -description

Exposes a validation, merge, or commit completion event delegate.

## -inheritance

## -remarks

An event sink that implements **IPrintSchemaAsyncOperationEvent** and the event source, [IPrintSchemaAsyncOperation](./nn-printerextension-iprintschemaasyncoperation.md) are connected via the [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) mechanism. You must retrieve a pointer to the **IConnectionPoint** interface by invoking **QueryInterface** on the **IPrinterQueue** object.

> [!NOTE]
> It is mandatory to implement **IDispatch::Invoke** on the event sink that implements **IPrinterQueueEvent**, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the **IDispatch** interface.

## -see-also

[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)

[IPrintSchemaAsyncOperation](./nn-printerextension-iprintschemaasyncoperation.md)
