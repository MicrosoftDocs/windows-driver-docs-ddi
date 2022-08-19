---
UID: NF:printerextension.IPrinterExtensionEvent.OnPrinterQueuesEnumerated
title: IPrinterExtensionEvent::OnPrinterQueuesEnumerated (printerextension.h)
description: Called when printer queues are enumerated.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterExtensionEvent::OnPrinterQueuesEnumerated"]
ms.keywords: IPrinterExtensionEvent interface [Print Devices],OnPrinterQueuesEnumerated method, IPrinterExtensionEvent.OnPrinterQueuesEnumerated, IPrinterExtensionEvent::OnPrinterQueuesEnumerated, OnPrinterQueuesEnumerated, OnPrinterQueuesEnumerated method [Print Devices], OnPrinterQueuesEnumerated method [Print Devices],IPrinterExtensionEvent interface, print.iprinterextensionevent_onprinterqueuesenumerated, printerextension/IPrinterExtensionEvent::OnPrinterQueuesEnumerated
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - IPrinterExtensionEvent::OnPrinterQueuesEnumerated
 - printerextension/IPrinterExtensionEvent::OnPrinterQueuesEnumerated
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionEvent::OnPrinterQueuesEnumerated
---

## -description

Called when printer queues are enumerated.

## -parameters

### -param pContextCollection [in]

Pointer to [IPrinterExtensionContextCollection](./nn-printerextension-iprinterextensioncontextcollection.md) object.

## -returns

This method returns an **HRESULT** value.

## -remarks

**OnPrinterQueuesEnumerated** is called every time the set of print queues associated with the printer extension is updated. So it is important for printer extensions to be able to handle multiple calls to this method without causing a catastrophic failure of the printer extension.

## -see-also

[IPrinterExtensionContext](./nn-printerextension-iprinterextensioncontext.md)

[IPrinterExtensionContextCollection](./nn-printerextension-iprinterextensioncontextcollection.md)

[IPrinterExtensionEvent](./nn-printerextension-iprinterextensionevent.md)