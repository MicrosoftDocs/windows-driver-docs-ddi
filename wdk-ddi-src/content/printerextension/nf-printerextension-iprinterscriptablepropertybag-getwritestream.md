---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetWriteStream
title: IPrinterScriptablePropertyBag::GetWriteStream (printerextension.h)
description: Gets a stream and uses it to write to a stream property.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterScriptablePropertyBag::GetWriteStream"]
ms.keywords: GetWriteStream, GetWriteStream method [Print Devices], GetWriteStream method [Print Devices],IPrinterScriptablePropertyBag interface, IPrinterScriptablePropertyBag interface [Print Devices],GetWriteStream method, IPrinterScriptablePropertyBag.GetWriteStream, IPrinterScriptablePropertyBag::GetWriteStream, print.iprinterscriptablepropertybag_getwritestream, printerextension/IPrinterScriptablePropertyBag::GetWriteStream
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
 - IPrinterScriptablePropertyBag::GetWriteStream
 - printerextension/IPrinterScriptablePropertyBag::GetWriteStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag::GetWriteStream
---

## -description

Gets a stream and uses it  to write to a stream property.

## -parameters

### -param bstrName [in]

The property to write.

### -param ppStream [out, retval]

The retrieved stream.

## -returns

This method returns an **HRESULT** value.

## -remarks

**GetWriteStream** does not work with non-stream properties.

A call to **GetWriteStream** will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## -see-also

[IPrinterScriptablePropertyBag](./nn-printerextension-iprinterscriptablepropertybag.md)

[IPrinterScriptableStream](./nn-printerextension-iprinterscriptablestream.md)