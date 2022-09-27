---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetBool
title: IPrinterScriptablePropertyBag::GetBool (printerextension.h)
description: Gets a specified boolean property.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterScriptablePropertyBag::GetBool"]
ms.keywords: GetBool, GetBool method [Print Devices], GetBool method [Print Devices],IPrinterScriptablePropertyBag interface, IPrinterScriptablePropertyBag interface [Print Devices],GetBool method, IPrinterScriptablePropertyBag.GetBool, IPrinterScriptablePropertyBag::GetBool, print.iprinterscriptablepropertybag_getbool, printerextension/IPrinterScriptablePropertyBag::GetBool
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
 - IPrinterScriptablePropertyBag::GetBool
 - printerextension/IPrinterScriptablePropertyBag::GetBool
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag::GetBool
---

## -description

Gets a specified boolean property.

## -parameters

### -param bstrName [in]

The name of the property.

### -param pbValue [out, retval]

The returned property value.

## -returns

This method returns an **HRESULT** value.

## -remarks

A call to **GetBool** will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## -see-also

[IPrinterScriptablePropertyBag](./nn-printerextension-iprinterscriptablepropertybag.md)