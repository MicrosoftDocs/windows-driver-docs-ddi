---
UID: NN:printerextension.IPrinterPropertyBag
title: IPrinterPropertyBag (printerextension.h)
description: Provides strongly-typed get and set methods.
tech.root: print
ms.date: 08/04/2022
keywords: ["IPrinterPropertyBag interface"]
ms.keywords: IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], IPrinterPropertyBag interface [Print Devices],described, print.iprinterpropertybag_interface, printerextension/IPrinterPropertyBag
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
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
 - IPrinterPropertyBag
 - printerextension/IPrinterPropertyBag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterPropertyBag
---

## -description

Provides strongly-typed **get** and **set** methods.

Note that the driver property bag uses the following GUID for its property store format ID:

```cpp
DEFINE_GUID(FMTID_PrinterPropertyBag, 0x75f9adca, 0x097d, 0x45c3, 0xa6, 0xe4, 0xba, 0xb2, 0x9e, 0x27, 0x6f, 0x3e);</dd>
```

The **IPrinterPropertyBag** interface is used by all the printer property bags, including driver property bag, user property bag, queue property bag, and DEVMODE property bag.

## -see-also

[IDispatch](/windows/win32/api/oaidl/nn-oaidl-idispatch)

[IPrinterExtensionContext::DriverProperties](./nf-printerextension-iprinterextensioncontext-get_driverproperties.md)

[IPrinterExtensionContext::UserProperties](./nf-printerextension-iprinterextensioncontext-get_userproperties.md)

[IPrinterQueue::GetProperties](./nf-printerextension-iprinterqueue-getproperties.md)

[IPrinterScriptablePropertyBag](./nn-printerextension-iprinterscriptablepropertybag.md)

[V4 Printer Driver Property Bags](/windows-hardware/drivers/print/v4-driver-property-bags)
