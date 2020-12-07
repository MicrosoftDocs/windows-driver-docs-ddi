---
UID: NN:printerextension.IPrinterScriptContext
title: IPrinterScriptContext (printerextension.h)
description: Passed to all third-party constraints JavaScript functions, and provides access to relevant objects.
old-location: print\iprinterscriptcontext.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrinterScriptContext interface"]
ms.keywords: IPrinterScriptContext, IPrinterScriptContext interface [Print Devices], IPrinterScriptContext interface [Print Devices],described, print.iprinterscriptcontext, printerextension/IPrinterScriptContext
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
 - IPrinterScriptContext
 - printerextension/IPrinterScriptContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptContext
---

# IPrinterScriptContext interface


## -description

Passed to all third-party constraints JavaScript functions, and provides access to relevant objects.

The **IPrinterScriptContext** interface has these properties.

| Property | Access type | Description |
| --- | --- | --- |
| [DriverProperties](./nf-printerextension-iprinterextensioncontext-get_driverproperties.md) | Read-only | Provides access to the driver property bag, if the property bag is present. |
| [QueueProperties](./nf-printerextension-iprinterscriptcontext-get_queueproperties.md) | Read-only | Provides access to the queue property bag, if the property bag is present.
| [UserProperties](./nf-printerextension-iprinterextensioncontext-get_userproperties.md) | Read-only | Provides access to the user property bag, if the property bag is present.

## -see-also

[V4 Printer Driver Property Bags](/windows-hardware/drivers/print/v4-driver-property-bags)
