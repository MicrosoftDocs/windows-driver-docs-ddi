---
UID: NF:printerextension.IPrinterScriptContext.get_UserProperties
title: IPrinterScriptContext::get_UserProperties (printerextension.h)
description: Provides access to the user property bag, if the property bag is present.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterScriptContext::get_UserProperties"]
ms.keywords: IPrinterScriptContext interface [Print Devices],UserProperties property, IPrinterScriptContext.UserProperties, IPrinterScriptContext.get_UserProperties, IPrinterScriptContext::UserProperties, IPrinterScriptContext::get_UserProperties, UserProperties property [Print Devices], UserProperties property [Print Devices],IPrinterScriptContext interface, get_UserProperties, print.iprinterscriptcontext_userproperties, printerextension/IPrinterScriptContext::UserProperties, printerextension/IPrinterScriptContext::get_UserProperties
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
 - IPrinterScriptContext::get_UserProperties
 - printerextension/IPrinterScriptContext::get_UserProperties
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptContext::get_UserProperties
---

## -description

Provides access to the user property bag, if the property bag is present.

This property is read-only.

## -remarks

The user property bag is not available in (constraint) JavaScript functions when the functions are called during de-spooling. Therefore JavaScript functions should be designed to handle the situation when there is a failure to retrieve the user property bag.

> [!NOTE]
> Although the **UserProperties** property is read-only, the user property bag is a read/write property bag.

## -see-also

[IPrinterScriptContext](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptcontext)

[IPrinterScriptablePropertyBag](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablepropertybag)
