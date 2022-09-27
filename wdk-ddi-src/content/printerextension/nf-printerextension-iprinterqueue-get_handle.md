---
UID: NF:printerextension.IPrinterQueue.get_Handle
title: IPrinterQueue::get_Handle (printerextension.h)
description: Gets the underlying native handle for this print queue.
tech.root: print
ms.date: 08/04/2022
keywords: ["IPrinterQueue::get_Handle"]
ms.keywords: Handle property [Print Devices], Handle property [Print Devices],IPrinterQueue interface, IPrinterQueue interface [Print Devices],Handle property, IPrinterQueue.Handle, IPrinterQueue.get_Handle, IPrinterQueue::Handle, IPrinterQueue::get_Handle, get_Handle, print.iprinterqueue_handle, printerextension/IPrinterQueue::Handle, printerextension/IPrinterQueue::get_Handle
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
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
 - IPrinterQueue::get_Handle
 - printerextension/IPrinterQueue::get_Handle
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterQueue::get_Handle
---

## -description

Gets the underlying native handle for this print queue.

This property is read-only.

## -parameters

### -param phPrinter

Defines the **HANDLE** parameter *phPrinter*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrinterQueue](./nn-printerextension-iprinterqueue.md)