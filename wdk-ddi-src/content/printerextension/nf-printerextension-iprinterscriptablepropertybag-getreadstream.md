---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetReadStream
title: IPrinterScriptablePropertyBag::GetReadStream (printerextension.h)
description: Gets a read stream and uses it to read from a property.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterScriptablePropertyBag::GetReadStream"]
ms.keywords: GetReadStream, GetReadStream method [Print Devices], GetReadStream method [Print Devices],IPrinterScriptablePropertyBag interface, IPrinterScriptablePropertyBag interface [Print Devices],GetReadStream method, IPrinterScriptablePropertyBag.GetReadStream, IPrinterScriptablePropertyBag::GetReadStream, print.iprinterscriptablepropertybag_getreadstream, printerextension/IPrinterScriptablePropertyBag::GetReadStream
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
 - IPrinterScriptablePropertyBag::GetReadStream
 - printerextension/IPrinterScriptablePropertyBag::GetReadStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag::GetReadStream
---

## -description

Gets a read stream and uses it to read  from a property.

## -parameters

### -param bstrName [in]

The property to read.

### -param ppStream [out, retval]

The returned stream.

## -returns

This method returns an **HRESULT** value.

## -remarks

**GetReadStream** does not work with non-stream properties.

A call to **GetReadStream** will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## -see-also

[IPrinterScriptablePropertyBag](./nn-printerextension-iprinterscriptablepropertybag.md)

[IPrinterScriptableStream](./nn-printerextension-iprinterscriptablestream.md)