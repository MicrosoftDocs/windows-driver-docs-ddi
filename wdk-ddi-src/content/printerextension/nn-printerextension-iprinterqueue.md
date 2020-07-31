---
UID: NN:printerextension.IPrinterQueue
title: IPrinterQueue (printerextension.h)
description: Represents a single printer queue.
old-location: print\iprinterqueue_interface.htm
tech.root: print
ms.assetid: 2DB57234-E783-4C6B-A743-F1E9F7D34D97
ms.date: 04/20/2018
keywords: ["IPrinterQueue interface"]
ms.keywords: IPrinterQueue, IPrinterQueue interface [Print Devices], IPrinterQueue interface [Print Devices],described, print.iprinterqueue_interface, printerextension/IPrinterQueue
f1_keywords:
 - "printerextension/IPrinterQueue"
 - "IPrinterQueue"
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
- IPrinterQueue
targetos: Windows
req.typenames: 
---

# IPrinterQueue interface

## -description

Represents a single printer queue.

## -inheritance

## -remarks

Any event sink that implements [IPrinterQueueEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterqueueevent) is connected to the associated event source, **IPrinterQueue**, via the [IConnectionPoint](https://docs.microsoft.com/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint) mechanism. You must retrieve a pointer to the **IConnectionPoint** interface by invoking **QueryInterface** on the **IPrinterQueue** object.

> [!NOTE]
> It is mandatory to implement **IDispatch::Invoke** on the event sink that implements **IPrinterQueueEvent**, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the **IDispatch** interface.

## -see-also

[IConnectionPoint](https://docs.microsoft.com/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint)

[IPrinterQueueEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterqueueevent)
