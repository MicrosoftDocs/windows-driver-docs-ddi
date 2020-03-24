---
UID: NN:printerextension.IPrinterScriptContext
title: IPrinterScriptContext (printerextension.h)
description: Passed to all third-party constraints JavaScript functions, and provides access to relevant objects.
old-location: print\iprinterscriptcontext.htm
tech.root: print
ms.assetid: B44B47EA-6848-430E-9C10-F6DD460C2304
ms.date: 04/20/2018
keywords: ["IPrinterScriptContext interface"]
ms.keywords: IPrinterScriptContext, IPrinterScriptContext interface [Print Devices], IPrinterScriptContext interface [Print Devices],described, print.iprinterscriptcontext, printerextension/IPrinterScriptContext
f1_keywords:
 - "printerextension/IPrinterScriptContext"
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
- IPrinterScriptContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptContext interface

## -description

Passed to all third-party constraints JavaScript functions, and provides access to relevant objects.

The **IPrinterScriptContext** interface has these properties.

| Property | Access type | Description |
| --- | --- | --- |
| [DriverProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterextensioncontext-get_driverproperties) | Read-only | Provides access to the driver property bag, if the property bag is present. |
| [QueueProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterscriptcontext-get_queueproperties) | Read-only | Provides access to the queue property bag, if the property bag is present.
| [UserProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterextensioncontext-get_userproperties) | Read-only | Provides access to the user property bag, if the property bag is present.

## -see-also

[V4 Printer Driver Property Bags](https://docs.microsoft.com/windows-hardware/drivers/print/v4-driver-property-bags)
