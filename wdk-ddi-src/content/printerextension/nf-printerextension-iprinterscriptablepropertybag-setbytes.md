---
UID: NF:printerextension.IPrinterScriptablePropertyBag.SetBytes
title: IPrinterScriptablePropertyBag::SetBytes (printerextension.h)
description: Learn how this method writes a byte array property.
tech.root: print
ms.date: 08/04/2022
keywords: ["IPrinterScriptablePropertyBag::SetBytes"]
ms.keywords: IPrinterScriptablePropertyBag interface [Print Devices],SetBytes method, IPrinterScriptablePropertyBag.SetBytes, IPrinterScriptablePropertyBag::SetBytes, SetBytes, SetBytes method [Print Devices], SetBytes method [Print Devices],IPrinterScriptablePropertyBag interface, print.iprinterscriptablepropertybag_setbytes, printerextension/IPrinterScriptablePropertyBag::SetBytes
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
 - IPrinterScriptablePropertyBag::SetBytes
 - printerextension/IPrinterScriptablePropertyBag::SetBytes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag::SetBytes
---

## -description

Writes a byte array property.

## -parameters

### -param bstrName [in]

The array to write to.

### -param pArray

The JavaScript array to write.

## -returns

This method returns an **HRESULT** value.

## -remarks

A call to **SetBytes** will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## -see-also

[IPrinterScriptablePropertyBag](./nn-printerextension-iprinterscriptablepropertybag.md)