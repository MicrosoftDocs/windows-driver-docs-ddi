---
UID: NF:printerextension.IPrinterPropertyBag.SetInt32
title: IPrinterPropertyBag::SetInt32 (printerextension.h)
description: Writes an integer property.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterPropertyBag::SetInt32"]
ms.keywords: IPrinterPropertyBag interface [Print Devices],SetInt32 method, IPrinterPropertyBag.SetInt32, IPrinterPropertyBag::SetInt32, SetInt32, SetInt32 method [Print Devices], SetInt32 method [Print Devices],IPrinterPropertyBag interface, print.iprinterpropertybag_setint32, printerextension/IPrinterPropertyBag::SetInt32
req.header: printerextension.h
req.include-header: Printerextension.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
 - IPrinterPropertyBag::SetInt32
 - printerextension/IPrinterPropertyBag::SetInt32
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterPropertyBag::SetInt32
---

# IPrinterPropertyBag::SetInt32

## -description

Writes an integer property.

## -parameters

### -param bstrName [in]

The property to set.

### -param nValue [in]

The new value to set.

## -returns

This method returns an **HRESULT** value.

## -remarks

In Windows 8.1 a new flag, PRINTER_ACCESS_MANAGE_LIMITED, has been introduced to grant print queue permissions that are more limited than PRINTER_ACCESS_ADMINISTER, but more powerful than
PRINTER_ACCESS_USE.

The permissions are a subset of those associated with PRINTER_ACCESS_ADMINISTER. This means that if the currently logged-on user has PRINTER_ACCESS_ADMINISTER permission, the user can gain
PRINTER_ACCESS_MANAGE_LIMITED access to the queue.

A call to set a property on a queue property bag will fail with ERROR_ACCESS_DENIED, if the user does not have the appropriate permission. This behavior was true before PRINTER_ACCESS_MANAGE_LIMITED was introduced, and it's still the current behavior.

## -see-also

[IPrinterPropertyBag](./nn-printerextension-iprinterpropertybag.md)