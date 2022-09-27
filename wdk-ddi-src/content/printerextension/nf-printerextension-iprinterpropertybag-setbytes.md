---
UID: NF:printerextension.IPrinterPropertyBag.SetBytes
title: IPrinterPropertyBag::SetBytes (printerextension.h)
description: Writes a byte array property.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrinterPropertyBag::SetBytes"]
ms.keywords: IPrinterPropertyBag interface [Print Devices],SetBytes method, IPrinterPropertyBag.SetBytes, IPrinterPropertyBag::SetBytes, SetBytes, SetBytes method [Print Devices], SetBytes method [Print Devices],IPrinterPropertyBag interface, print.iprinterpropertybag_setbytes, printerextension/IPrinterPropertyBag::SetBytes
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
 - IPrinterPropertyBag::SetBytes
 - printerextension/IPrinterPropertyBag::SetBytes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterPropertyBag::SetBytes
---

## -description

Writes a byte array property.

## -parameters

### -param bstrName [in]

The array to write to.

### -param cbValue [in]

The number of bytes to write.

### -param pValue

The values to write.

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