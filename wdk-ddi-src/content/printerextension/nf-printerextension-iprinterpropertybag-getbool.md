---
UID: NF:printerextension.IPrinterPropertyBag.GetBool
title: IPrinterPropertyBag::GetBool (printerextension.h)
description: Reads a specified boolean property.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterPropertyBag::GetBool"]
ms.keywords: GetBool, GetBool method [Print Devices], GetBool method [Print Devices],IPrinterPropertyBag interface, IPrinterPropertyBag interface [Print Devices],GetBool method, IPrinterPropertyBag.GetBool, IPrinterPropertyBag::GetBool, print.iprinterpropertybag_getbool, printerextension/IPrinterPropertyBag::GetBool
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
 - IPrinterPropertyBag::GetBool
 - printerextension/IPrinterPropertyBag::GetBool
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterPropertyBag::GetBool
---

## -description

Reads a specified boolean property.

## -parameters

### -param bstrName [in]

The name of the property.

### -param pbValue [out, retval]

The returned property value.

## -returns

This method returns an **HRESULT** value.

## -see-also

[IPrinterPropertyBag](./nn-printerextension-iprinterpropertybag.md)