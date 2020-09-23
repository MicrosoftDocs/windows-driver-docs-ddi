---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetString
title: IPrinterScriptablePropertyBag::GetString (printerextension.h)
description: Gets a string property.
old-location: print\iprinterscriptablepropertybag_getstring.htm
tech.root: print
ms.assetid: FA14B81D-0B51-4C07-96BC-38CAABED735A
ms.date: 04/20/2018
keywords: ["IPrinterScriptablePropertyBag::GetString"]
ms.keywords: GetString, GetString method [Print Devices], GetString method [Print Devices],IPrinterScriptablePropertyBag interface, IPrinterScriptablePropertyBag interface [Print Devices],GetString method, IPrinterScriptablePropertyBag.GetString, IPrinterScriptablePropertyBag::GetString, print.iprinterscriptablepropertybag_getstring, printerextension/IPrinterScriptablePropertyBag::GetString
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
 - IPrinterScriptablePropertyBag::GetString
 - printerextension/IPrinterScriptablePropertyBag::GetString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag.GetString
---

# IPrinterScriptablePropertyBag::GetString


## -description

Gets a string property.

## -parameters

### -param bstrName 

[in]
The property to read.

### -param pbstrValue 

[out, retval]
        The value read.

## -returns

This method returns an <b>HRESULT</b> value.

## -remarks

A call to <b>GetString</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablepropertybag">IPrinterScriptablePropertyBag</a>