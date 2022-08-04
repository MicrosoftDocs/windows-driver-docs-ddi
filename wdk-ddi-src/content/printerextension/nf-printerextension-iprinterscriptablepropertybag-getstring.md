---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetString
title: IPrinterScriptablePropertyBag::GetString (printerextension.h)
description: Gets a string property.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterScriptablePropertyBag::GetString"]
ms.keywords: GetString, GetString method [Print Devices], GetString method [Print Devices],IPrinterScriptablePropertyBag interface, IPrinterScriptablePropertyBag interface [Print Devices],GetString method, IPrinterScriptablePropertyBag.GetString, IPrinterScriptablePropertyBag::GetString, print.iprinterscriptablepropertybag_getstring, printerextension/IPrinterScriptablePropertyBag::GetString
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
 - IPrinterScriptablePropertyBag::GetString
---

## -description

Gets a string property.

## -parameters

### -param bstrName [in]

The property to read.

### -param pbstrValue [out, retval]

The value read.

## -returns

This method returns an **HRESULT** value.

## -remarks

A call to **GetString** will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## -see-also

[IPrinterScriptablePropertyBag](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablepropertybag)
