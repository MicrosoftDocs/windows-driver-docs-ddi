---
UID: NF:printerextension.IPrinterScriptContext.get_DriverProperties
title: IPrinterScriptContext::get_DriverProperties (printerextension.h)
description: Provides access to the driver property bag, if the property bag is present.
tech.root: print
ms.date: 08/04/2022
keywords: ["IPrinterScriptContext::get_DriverProperties"]
ms.keywords: DriverProperties property [Print Devices], DriverProperties property [Print Devices],IPrinterScriptContext interface, IPrinterScriptContext interface [Print Devices],DriverProperties property, IPrinterScriptContext.DriverProperties, IPrinterScriptContext.get_DriverProperties, IPrinterScriptContext::DriverProperties, IPrinterScriptContext::get_DriverProperties, get_DriverProperties, print.iprinterscriptcontext_driverproperties, printerextension/IPrinterScriptContext::DriverProperties, printerextension/IPrinterScriptContext::get_DriverProperties
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
 - IPrinterScriptContext::get_DriverProperties
 - printerextension/IPrinterScriptContext::get_DriverProperties
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptContext::get_DriverProperties
---

## -description

Provides access to the driver property bag, if the property bag is present.

This property is read-only.

## -parameters

### -param ppPropertyBag

Defines the **IPrinterScriptablePropertyBag** parameter *ppPropertyBag*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrinterScriptContext](./nn-printerextension-iprinterscriptcontext.md)

[IPrinterScriptablePropertyBag](./nn-printerextension-iprinterscriptablepropertybag.md)