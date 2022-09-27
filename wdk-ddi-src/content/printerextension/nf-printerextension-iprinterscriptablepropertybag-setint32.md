---
UID: NF:printerextension.IPrinterScriptablePropertyBag.SetInt32
title: IPrinterScriptablePropertyBag::SetInt32 (printerextension.h)
description: Learn how this method writes an integer property.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterScriptablePropertyBag::SetInt32"]
ms.keywords: IPrinterScriptablePropertyBag interface [Print Devices],SetInt32 method, IPrinterScriptablePropertyBag.SetInt32, IPrinterScriptablePropertyBag::SetInt32, SetInt32, SetInt32 method [Print Devices], SetInt32 method [Print Devices],IPrinterScriptablePropertyBag interface, print.iprinterscriptablepropertybag_setint32, printerextension/IPrinterScriptablePropertyBag::SetInt32
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
 - IPrinterScriptablePropertyBag::SetInt32
 - printerextension/IPrinterScriptablePropertyBag::SetInt32
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag::SetInt32
---

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

A call to **SetInt32** will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## -see-also

[IPrinterScriptablePropertyBag](./nn-printerextension-iprinterscriptablepropertybag.md)