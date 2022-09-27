---
UID: NF:printerextension.IPrinterExtensionContext.get_UserProperties
title: IPrinterExtensionContext::get_UserProperties (printerextension.h)
description: Gets the user property bag for this app.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrinterExtensionContext::get_UserProperties"]
ms.keywords: IPrinterExtensionContext interface [Print Devices],UserProperties property, IPrinterExtensionContext.UserProperties, IPrinterExtensionContext.get_UserProperties, IPrinterExtensionContext::UserProperties, IPrinterExtensionContext::get_UserProperties, UserProperties property [Print Devices], UserProperties property [Print Devices],IPrinterExtensionContext interface, get_UserProperties, print.iprinterextensioncontext_userproperties, printerextension/IPrinterExtensionContext::UserProperties, printerextension/IPrinterExtensionContext::get_UserProperties
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
 - IPrinterExtensionContext::get_UserProperties
 - printerextension/IPrinterExtensionContext::get_UserProperties
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionContext::get_UserProperties
---

# IPrinterExtensionContext::get_UserProperties

## -description

Gets the user property bag for this app.

This property is read-only.

## -parameters

### -param ppPropertyBag

Defines the **IPrinterPropertyBag** parameter *ppPropertyBag*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrinterExtensionContext](./nn-printerextension-iprinterextensioncontext.md)

[IPrinterPropertyBag](./nn-printerextension-iprinterpropertybag.md)