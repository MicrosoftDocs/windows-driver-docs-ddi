---
UID: NF:printerextension.IPrinterScriptablePropertyBag.SetBool
title: IPrinterScriptablePropertyBag::SetBool (printerextension.h)
description: Writes a specified boolean property value.
old-location: print\iprinterscriptablepropertybag_setbool.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrinterScriptablePropertyBag::SetBool"]
ms.keywords: IPrinterScriptablePropertyBag interface [Print Devices],SetBool method, IPrinterScriptablePropertyBag.SetBool, IPrinterScriptablePropertyBag::SetBool, SetBool, SetBool method [Print Devices], SetBool method [Print Devices],IPrinterScriptablePropertyBag interface, print.iprinterscriptablepropertybag_setbool, printerextension/IPrinterScriptablePropertyBag::SetBool
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
 - IPrinterScriptablePropertyBag::SetBool
 - printerextension/IPrinterScriptablePropertyBag::SetBool
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag::SetBool
---

# IPrinterScriptablePropertyBag::SetBool


## -description

Writes a specified boolean property value.

## -parameters

### -param bstrName 

[in]
The property to set.

### -param bValue 

[in]
The value to set.

## -returns

This method returns an <b>HRESULT</b> value.

## -remarks

A call to <b>SetBool</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablepropertybag">IPrinterScriptablePropertyBag</a>

