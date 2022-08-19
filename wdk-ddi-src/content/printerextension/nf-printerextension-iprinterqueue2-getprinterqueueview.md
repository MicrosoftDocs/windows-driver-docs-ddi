---
UID: NF:printerextension.IPrinterQueue2.GetPrinterQueueView
title: IPrinterQueue2::GetPrinterQueueView (printerextension.h)
description: Retrieves an IPrinterQueueView object, and initializes the object with the range of jobs to be monitored.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterQueue2::GetPrinterQueueView"]
ms.keywords: GetPrinterQueueView, GetPrinterQueueView method [Print Devices], GetPrinterQueueView method [Print Devices],IPrinterQueue2 interface, IPrinterQueue2 interface [Print Devices],GetPrinterQueueView method, IPrinterQueue2.GetPrinterQueueView, IPrinterQueue2::GetPrinterQueueView, print.iprinterqueue2_getprinterqueueview, printerextension/IPrinterQueue2::GetPrinterQueueView
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
 - IPrinterQueue2::GetPrinterQueueView
 - printerextension/IPrinterQueue2::GetPrinterQueueView
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterQueue2::GetPrinterQueueView
---

## -description

Retrieves an [IPrinterQueueView](./nn-printerextension-iprinterqueueview.md) object, and initializes the object with the range of jobs to be monitored.

This method allows the user to perform job management tasks from within a UWP device app for printers.

## -parameters

### -param ulViewOffset [in]

Indicates the start of the range of jobs to be monitored.

### -param ulViewSize [in]

Indicates the size or the range of jobs to be monitored.

### -param ppJobView [out, retval]

IPrinterQueueView object that shows the range of jobs to be monitored.

## -returns

If the method call is successful, **GetPrinterQueueView** returns S_OK.

Otherwise, if a call to **GetPrinterQueueView** results in an error condition, then one of the following **HRESULT** values can be returned.

| HRESULT value | Description |
|--|--|
| E_ILLEGAL_METHOD_CALL | Indicates an attempt to retrieve more than one printer queue view object. |
| E_INVALIDARG | Indicates an attempt to create a view size larger than the maximum size. |

## -remarks

Only one [IPrinterQueueView](./nn-printerextension-iprinterqueueview.md) object can be retrieved per [IPrinterQueue2](./nn-printerextension-iprinterqueue2.md) object.
However it is possible to move around the single view that you retrieve. In other words, it is possible to  change the positions of the monitored jobs by invoking [IPrinterQueueView::SetViewRange](./nf-printerextension-iprinterqueueview-setviewrange.md).

> [!NOTE]
> There is work underway to implement a cap on the maximum size of the printer queue view.

## -see-also

[IPrinterQueue2](./nn-printerextension-iprinterqueue2.md)

[IPrinterQueueView](./nn-printerextension-iprinterqueueview.md)