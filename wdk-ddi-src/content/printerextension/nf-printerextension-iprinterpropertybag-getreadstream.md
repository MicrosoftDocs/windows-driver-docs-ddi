---
UID: NF:printerextension.IPrinterPropertyBag.GetReadStream
title: IPrinterPropertyBag::GetReadStream (printerextension.h)
description: Gets a stream in order to read from a stream property.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrinterPropertyBag::GetReadStream"]
ms.keywords: GetReadStream, GetReadStream method [Print Devices], GetReadStream method [Print Devices],IPrinterPropertyBag interface, IPrinterPropertyBag interface [Print Devices],GetReadStream method, IPrinterPropertyBag.GetReadStream, IPrinterPropertyBag::GetReadStream, print.iprinterpropertybag_getreadstream, printerextension/IPrinterPropertyBag::GetReadStream
req.header: printerextension.h
req.include-header: Printerextension.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
 - IPrinterPropertyBag::GetReadStream
 - printerextension/IPrinterPropertyBag::GetReadStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterPropertyBag::GetReadStream
---

## -description

Gets a stream in order to read from a stream property.

## -parameters

### -param bstrName [in]

The property to read.

### -param ppValue

The returned stream.

## -returns

This method returns an **HRESULT** value.

## -remarks

This method does not work with non-stream properties.

## -see-also

[IPrinterPropertyBag](./nn-printerextension-iprinterpropertybag.md)