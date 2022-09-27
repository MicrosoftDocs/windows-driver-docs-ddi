---
UID: NF:printerextension.IPrinterScriptableStream.Seek
title: IPrinterScriptableStream::Seek (printerextension.h)
description: Sets the seek pointer.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterScriptableStream::Seek"]
ms.keywords: IPrinterScriptableStream interface [Print Devices],Seek method, IPrinterScriptableStream.Seek, IPrinterScriptableStream::Seek, Seek, Seek method [Print Devices], Seek method [Print Devices],IPrinterScriptableStream interface, print.iprinterscriptablestream__seek, printerextension/IPrinterScriptableStream::Seek
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
 - IPrinterScriptableStream::Seek
 - printerextension/IPrinterScriptableStream::Seek
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptableStream::Seek
---

## -description

Sets the seek pointer.

## -parameters

### -param lOffset [in]

The displacement to be added to the location indicated by the *streamSeek* parameter.

### -param streamSeek [in]

The origin for the displacement specified *lOffset*.

### -param plPosition [out, retval]

The new pointer position.

## -returns

This method returns an **HRESULT** value.

## -see-also

[IPrinterScriptableStream](./nn-printerextension-iprinterscriptablestream.md)