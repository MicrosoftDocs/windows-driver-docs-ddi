---
UID: NF:printerextension.IPrinterScriptableSequentialStream.Write
title: IPrinterScriptableSequentialStream::Write (printerextension.h)
description: The Write method writes the provided JavaScript array to the stream and returns the number of bytes written.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterScriptableSequentialStream::Write"]
ms.keywords: IPrinterScriptableSequentialStream interface [Print Devices],Write method, IPrinterScriptableSequentialStream.Write, IPrinterScriptableSequentialStream::Write, Write, Write method [Print Devices], Write method [Print Devices],IPrinterScriptableSequentialStream interface, print.iprinterscriptablesequentialstream_write, printerextension/IPrinterScriptableSequentialStream::Write
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
 - IPrinterScriptableSequentialStream::Write
 - printerextension/IPrinterScriptableSequentialStream::Write
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - printerextension.h
api_name:
 - IPrinterScriptableSequentialStream::Write
---

## -description

The Write method writes the provided JavaScript array to the stream and returns the number of bytes written.

## -parameters

### -param pArray

The array to write.

### -param pcbWritten [out, retval]

The number of bytes written.

## -returns

This method returns an **HRESULT** value.

## -see-also

[IPrinterScriptableSequentialStream](./nn-printerextension-iprinterscriptablesequentialstream.md)