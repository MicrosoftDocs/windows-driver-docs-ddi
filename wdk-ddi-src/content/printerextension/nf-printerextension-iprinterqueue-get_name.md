---
UID: NF:printerextension.IPrinterQueue.get_Name
title: IPrinterQueue::get_Name (printerextension.h)
description: Gets the name of the printer for this print queue.
tech.root: print
ms.date: 08/04/2022
keywords: ["IPrinterQueue::get_Name"]
ms.keywords: IPrinterQueue interface [Print Devices],Name property, IPrinterQueue.Name, IPrinterQueue.get_Name, IPrinterQueue::Name, IPrinterQueue::get_Name, Name property [Print Devices], Name property [Print Devices],IPrinterQueue interface, get_Name, print.iprinterqueue_name, printerextension/IPrinterQueue::Name, printerextension/IPrinterQueue::get_Name
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
 - IPrinterQueue::get_Name
 - printerextension/IPrinterQueue::get_Name
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterQueue::get_Name
---

# IPrinterQueue::get_Name

## -description

Gets the name of the printer for this print queue.

This property is read-only.

## -parameters

### -param pbstrName

Defines the **BSTR** parameter *pbstrName*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrinterQueue](./nn-printerextension-iprinterqueue.md)