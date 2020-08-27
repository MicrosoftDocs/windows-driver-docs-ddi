---
UID: NN:printerextension.IPrintSchemaAsyncOperationEvent
title: IPrintSchemaAsyncOperationEvent (printerextension.h)
description: Exposes a validation, merge, or commit completion event delegate.
old-location: print\iprintschemaasyncoperationevent_interface.htm
tech.root: print
ms.assetid: 4ADF74C0-F196-476F-889D-EB1A0B881920
ms.date: 04/20/2018
keywords: ["IPrintSchemaAsyncOperationEvent interface"]
ms.keywords: IPrintSchemaAsyncOperationEvent, IPrintSchemaAsyncOperationEvent interface [Print Devices], IPrintSchemaAsyncOperationEvent interface [Print Devices],described, print.iprintschemaasyncoperationevent_interface, printerextension/IPrintSchemaAsyncOperationEvent
f1_keywords:
 - "printerextension/IPrintSchemaAsyncOperationEvent"
 - "IPrintSchemaAsyncOperationEvent"
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
- IPrintSchemaAsyncOperationEvent
targetos: Windows
req.typenames: 
---

# IPrintSchemaAsyncOperationEvent interface

## -description

Exposes a validation, merge, or commit completion event delegate.

## -inheritance

## -remarks

An event sink that implements **IPrintSchemaAsyncOperationEvent** and the event source, [IPrintSchemaAsyncOperation](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaasyncoperation) are connected via the [IConnectionPoint](https://docs.microsoft.com/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) mechanism. You must retrieve a pointer to the **IConnectionPoint** interface by invoking **QueryInterface** on the **IPrinterQueue** object.

> [!NOTE]
> It is mandatory to implement **IDispatch::Invoke** on the event sink that implements **IPrinterQueueEvent**, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the **IDispatch** interface.

## -see-also

[IConnectionPoint](https://docs.microsoft.com/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)

[IPrintSchemaAsyncOperation](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaasyncoperation)
