---
UID: NF:printerextension.IPrinterExtensionAsyncOperation.Cancel
title: IPrinterExtensionAsyncOperation::Cancel (printerextension.h)
description: Cancels the asynchronous operation.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrinterExtensionAsyncOperation::Cancel"]
ms.keywords: Cancel, Cancel method [Print Devices], Cancel method [Print Devices],IPrinterExtensionAsyncOperation interface, IPrinterExtensionAsyncOperation interface [Print Devices],Cancel method, IPrinterExtensionAsyncOperation.Cancel, IPrinterExtensionAsyncOperation::Cancel, print.iprinterextensionasyncoperation_cancel, printerextension/IPrinterExtensionAsyncOperation::Cancel
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
 - IPrinterExtensionAsyncOperation::Cancel
 - printerextension/IPrinterExtensionAsyncOperation::Cancel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionAsyncOperation::Cancel
---

## -description

Cancels the asynchronous operation.

## -returns

This method returns an **HRESULT** value.

## -remarks

This method guarantees that the callback object will not be invoked. No other form of status is provided, such as a way to check to see if the operation has been canceled.
Also, note that this method does not wait for the cancellation to be processed - it returns immediately.

## -see-also

[IPrinterExtensionAsyncOperation](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensionasyncoperation)
