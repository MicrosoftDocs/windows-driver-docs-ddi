---
UID: NF:printerextension.IPrinterPropertyBag.GetString
title: IPrinterPropertyBag::GetString (printerextension.h)
description: Reads a string property.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterPropertyBag::GetString"]
ms.keywords: GetString, GetString method [Print Devices], GetString method [Print Devices],IPrinterPropertyBag interface, IPrinterPropertyBag interface [Print Devices],GetString method, IPrinterPropertyBag.GetString, IPrinterPropertyBag::GetString, print.iprinterpropertybag_getstring, printerextension/IPrinterPropertyBag::GetString
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
 - IPrinterPropertyBag::GetString
 - printerextension/IPrinterPropertyBag::GetString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterPropertyBag::GetString
---

## -description

Reads a string property.

## -parameters

### -param bstrName [in]

The property to read.

### -param pbstrValue [out, retval]

The value read.

## -returns

This method returns an **HRESULT** value.

## -see-also

[IPrinterPropertyBag](./nn-printerextension-iprinterpropertybag.md)