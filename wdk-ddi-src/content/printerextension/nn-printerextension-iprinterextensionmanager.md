---
UID: NN:printerextension.IPrinterExtensionManager
title: IPrinterExtensionManager (printerextension.h)
description: The IPrinterExtensionManager interface is retrieved by CoCreating the PrinterExtensionManager class.
tech.root: print
ms.date: 06/11/2021
keywords: ["IPrinterExtensionManager interface"]
ms.keywords: IPrinterExtensionManager, IPrinterExtensionManager interface [Print Devices], IPrinterExtensionManager interface [Print Devices],described, print.iprinterextensionmanager_interface, printerextension/IPrinterExtensionManager
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
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
 - IPrinterExtensionManager
 - printerextension/IPrinterExtensionManager
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - printerextension.h
api_name:
 - IPrinterExtensionManager
---

# IPrinterExtensionManager interface

## -description

The **IPrinterExtensionManager** interface is retrieved by CoCreating the **PrinterExtensionManager** class.

## -inheritance

The **IPrinterExtensionManager** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

## -remarks

Any event sink that implements [IPrinterExtensionEvent](./nn-printerextension-iprinterextensionevent.md) is connected to the associated event source, **IPrinterExtensionManager**, via the **IConnectionPoint** mechanism. You must retrieve a pointer to the **IConnectionPoint** interface by invoking **QueryInterface** on the **IPrinterExtensionManager** object.

It is mandatory to implement **IDispatch::Invoke** on the event sink that implements **IPrinterExtensionEvent**, since that is the mechanism via which events are raised.

It is sufficient to provide stub implementations of the other methods on the **IDispatch** interface.