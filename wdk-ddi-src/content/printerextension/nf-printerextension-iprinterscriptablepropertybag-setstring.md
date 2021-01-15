---
UID: NF:printerextension.IPrinterScriptablePropertyBag.SetString
title: IPrinterScriptablePropertyBag::SetString (printerextension.h)
description: Writes a string property.
old-location: print\iprinterscriptablepropertybag_setstring.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrinterScriptablePropertyBag::SetString"]
ms.keywords: IPrinterScriptablePropertyBag interface [Print Devices],SetString method, IPrinterScriptablePropertyBag.SetString, IPrinterScriptablePropertyBag::SetString, SetString, SetString method [Print Devices], SetString method [Print Devices],IPrinterScriptablePropertyBag interface, print.iprinterscriptablepropertybag_setstring, printerextension/IPrinterScriptablePropertyBag::SetString
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
 - IPrinterScriptablePropertyBag::SetString
 - printerextension/IPrinterScriptablePropertyBag::SetString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag::SetString
---

# IPrinterScriptablePropertyBag::SetString


## -description

Writes a string property.

## -parameters

### -param bstrName 

[in]
The property to set.

### -param bstrValue 

[in]
The property value to set.

## -returns

This method returns an <b>HRESULT</b> value.

## -remarks

A call to <b>SetString</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablepropertybag">IPrinterScriptablePropertyBag</a>

