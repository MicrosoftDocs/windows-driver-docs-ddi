---
UID: NN:printerextension.IPrinterScriptablePropertyBag
title: IPrinterScriptablePropertyBag (printerextension.h)
description: The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients.
tech.root: print
ms.date: 06/11/2021
keywords: ["IPrinterScriptablePropertyBag interface"]
ms.keywords: IPrinterScriptablePropertyBag, IPrinterScriptablePropertyBag interface [Print Devices], IPrinterScriptablePropertyBag interface [Print Devices],described, print.iprinterscriptablepropertybag, printerextension/IPrinterScriptablePropertyBag
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
 - IPrinterScriptablePropertyBag
 - printerextension/IPrinterScriptablePropertyBag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag
---

# IPrinterScriptablePropertyBag interface

## -description

The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients.

This interface is the same as [IPrinterPropertyBag](./nn-printerextension-iprinterpropertybag.md), except that the GetBytes and SetBytes methods operate on JavaScript arrays and the GetReadStream and GetWriteStream methods operate on [IPrinterScriptableStream](./nn-printerextension-iprinterscriptablestream.md) objects.

## -inheritance

The **IPrinterScriptablePropertyBag** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

## -see-also

[IPrinterPropertyBag](./nn-printerextension-iprinterpropertybag.md)

[IPrinterScriptContext::DriverProperties](./nf-printerextension-iprinterscriptcontext-get_driverproperties.md)

[IPrinterScriptContext::QueueProperties](./nf-printerextension-iprinterscriptcontext-get_queueproperties.md)

[IPrinterScriptContext::UserProperties](./nf-printerextension-iprinterscriptcontext-get_userproperties.md)

[IPrinterScriptableStream](./nn-printerextension-iprinterscriptablestream.md)

[V4 Printer Driver Property Bags](/windows-hardware/drivers/print/v4-driver-property-bags)