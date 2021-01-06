---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetInt32
title: IPrinterScriptablePropertyBag::GetInt32 (printerextension.h)
description: Gets an integer property.
old-location: print\iprinterscriptablepropertybag_getint32.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrinterScriptablePropertyBag::GetInt32"]
ms.keywords: GetInt32, GetInt32 method [Print Devices], GetInt32 method [Print Devices],IPrinterScriptablePropertyBag interface, IPrinterScriptablePropertyBag interface [Print Devices],GetInt32 method, IPrinterScriptablePropertyBag.GetInt32, IPrinterScriptablePropertyBag::GetInt32, print.iprinterscriptablepropertybag_getint32, printerextension/IPrinterScriptablePropertyBag::GetInt32
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
 - IPrinterScriptablePropertyBag::GetInt32
 - printerextension/IPrinterScriptablePropertyBag::GetInt32
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag.GetInt32
---

# IPrinterScriptablePropertyBag::GetInt32


## -description

Gets an integer property.

## -parameters

### -param bstrName 

[in]
The property to read.

### -param pnValue 

[out, retval]
The value read.

## -returns

This method returns an <b>HRESULT</b> value.

## -remarks

A call to <b>GetInt32</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablepropertybag">IPrinterScriptablePropertyBag</a>
