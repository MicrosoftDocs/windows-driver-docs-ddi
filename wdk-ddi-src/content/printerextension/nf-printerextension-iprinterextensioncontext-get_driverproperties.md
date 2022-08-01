---
UID: NF:printerextension.IPrinterExtensionContext.get_DriverProperties
title: IPrinterExtensionContext::get_DriverProperties (printerextension.h)
description: Gets the driver property bag.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrinterExtensionContext::get_DriverProperties"]
ms.keywords: DriverProperties property [Print Devices], DriverProperties property [Print Devices],IPrinterExtensionContext interface, IPrinterExtensionContext interface [Print Devices],DriverProperties property, IPrinterExtensionContext.DriverProperties, IPrinterExtensionContext.get_DriverProperties, IPrinterExtensionContext::DriverProperties, IPrinterExtensionContext::get_DriverProperties, get_DriverProperties, print.iprinterextensioncontext_driverproperties, printerextension/IPrinterExtensionContext::DriverProperties, printerextension/IPrinterExtensionContext::get_DriverProperties
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
 - IPrinterExtensionContext::get_DriverProperties
 - printerextension/IPrinterExtensionContext::get_DriverProperties
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionContext::get_DriverProperties
---

## -description

Gets the driver property bag.

This property is read-only.

## -remarks

The driver property bag uses the following GUID for its property store format ID:

```cpp
DEFINE_GUID(FMTID_PrinterPropertyBag, 0x75f9adca, 0x097d, 0x45c3, 0xa6, 0xe4, 0xba, 0xb2, 0x9e, 0x27, 0x6f, 0x3e);
```

## -see-also

[IPrinterExtensionContext](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensioncontext)

[IPrinterPropertyBag](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterpropertybag)
