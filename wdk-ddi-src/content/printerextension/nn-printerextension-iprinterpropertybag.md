---
UID: NN:printerextension.IPrinterPropertyBag
title: IPrinterPropertyBag (printerextension.h)
description: Provides strongly-typed get and set methods.
old-location: print\iprinterpropertybag_interface.htm
tech.root: print
ms.assetid: 421397FF-4956-4052-B63D-32F8E79A22D0
ms.date: 04/20/2018
ms.keywords: IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], IPrinterPropertyBag interface [Print Devices],described, print.iprinterpropertybag_interface, printerextension/IPrinterPropertyBag
ms.topic: interface
f1_keywords:
 - "printerextension/IPrinterPropertyBag"
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
- IPrinterPropertyBag
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterPropertyBag interface

## -description

Provides strongly-typed **get** and **set** methods.

Note that the driver property bag uses the following GUID for its property store format ID:

```cpp
DEFINE_GUID(FMTID_PrinterPropertyBag, 0x75f9adca, 0x097d, 0x45c3, 0xa6, 0xe4, 0xba, 0xb2, 0x9e, 0x27, 0x6f, 0x3e);</dd>
```

The **IPrinterPropertyBag** interface is used by all the printer property bags, including driver property bag, user property bag, queue property bag, and DEVMODE property bag.

## -inheritance

## -see-also

[IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch)

[IPrinterExtensionContext::DriverProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterextensioncontext-get_driverproperties)

[IPrinterExtensionContext::UserProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterextensioncontext-get_userproperties)

[IPrinterQueue::GetProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueue-getproperties)

[IPrinterScriptablePropertyBag](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablepropertybag)

[V4 Printer Driver Property Bags](https://docs.microsoft.com/windows-hardware/drivers/print/v4-driver-property-bags)
