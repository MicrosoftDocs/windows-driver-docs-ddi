---
UID: NN:printerextension.IPrinterQueueEvent
title: IPrinterQueueEvent (printerextension.h)
description: Provides the event delegate for printer queue events.
old-location: print\iprinterqueueevent_interface.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrinterQueueEvent interface"]
ms.keywords: IPrinterQueueEvent, IPrinterQueueEvent interface [Print Devices], IPrinterQueueEvent interface [Print Devices],described, print.iprinterqueueevent_interface, printerextension/IPrinterQueueEvent
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
 - IPrinterQueueEvent
 - printerextension/IPrinterQueueEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterQueueEvent
---

# IPrinterQueueEvent interface


## -description

Provides the event delegate for printer queue events.

## -inheritance

## -remarks

An event sink that implements **IPrinterQueueEvent** and the event source, [IPrinterQueue](./nn-printerextension-iprinterqueue.md) are connected via the [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) mechanism. You must retrieve a pointer to the **IConnectionPoint** interface by invoking **QueryInterface** on the **IPrinterQueue** object.

> [!NOTE]
> It is mandatory to implement **IDispatch::Invoke** on the event sink that implements **IPrinterQueueEvent**, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the **IDispatch** interface.

## -see-also

[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)

[IPrinterQueue](./nn-printerextension-iprinterqueue.md)
