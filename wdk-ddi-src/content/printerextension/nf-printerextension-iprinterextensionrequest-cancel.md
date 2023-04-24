---
UID: NF:printerextension.IPrinterExtensionRequest.Cancel
title: IPrinterExtensionRequest::Cancel (printerextension.h)
description: Completes the extension event with a cancellation.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrinterExtensionRequest::Cancel"]
ms.keywords: Cancel, Cancel method [Print Devices], Cancel method [Print Devices],IPrinterExtensionRequest interface, IPrinterExtensionRequest interface [Print Devices],Cancel method, IPrinterExtensionRequest.Cancel, IPrinterExtensionRequest::Cancel, print.iprinterextensionrequest_cancel, printerextension/IPrinterExtensionRequest::Cancel
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
 - IPrinterExtensionRequest::Cancel
 - printerextension/IPrinterExtensionRequest::Cancel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionRequest::Cancel
---

## -description

Completes the extension event with a cancellation.

## -parameters

### -param hrStatus

The operation result.

### -param bstrLogMessage [in]

The log message.

## -returns

This method returns an **HRESULT** value.

## -see-also

[IPrinterExtensionRequest](./nn-printerextension-iprinterextensionrequest.md)