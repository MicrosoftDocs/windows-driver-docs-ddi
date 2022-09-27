---
UID: NF:printerextension.IPrinterBidiSetRequestCallback.Completed
title: IPrinterBidiSetRequestCallback::Completed (printerextension.h)
description: Invoked when the Bidi "Set"" operation is completed.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrinterBidiSetRequestCallback::Completed"]
ms.keywords: Completed, Completed method [Print Devices], Completed method [Print Devices],IPrinterBidiSetRequestCallback interface, IPrinterBidiSetRequestCallback interface [Print Devices],Completed method, IPrinterBidiSetRequestCallback.Completed, IPrinterBidiSetRequestCallback::Completed, print.iprinterbidisetrequestcallback_completed, printerextension/IPrinterBidiSetRequestCallback::Completed
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - IPrinterBidiSetRequestCallback::Completed
 - printerextension/IPrinterBidiSetRequestCallback::Completed
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterBidiSetRequestCallback::Completed
---

## -description

Invoked when the Bidi "Set"" operation is completed.

## -parameters

### -param bstrResponse [in]

The received response.

### -param hrStatus [in]

An HRESULT value.

## -returns

This method returns the appropriate **HRESULT** value.

## -see-also

[IPrinterBidiSetRequestCallback](./nn-printerextension-iprinterbidisetrequestcallback.md)