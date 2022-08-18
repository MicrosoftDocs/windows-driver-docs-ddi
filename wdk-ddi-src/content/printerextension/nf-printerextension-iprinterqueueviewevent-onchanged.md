---
UID: NF:printerextension.IPrinterQueueViewEvent.OnChanged
title: IPrinterQueueViewEvent::OnChanged (printerextension.h)
description: Provides an IPrintJobCollection object that provides a snapshot of a range of print jobs in the queue.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterQueueViewEvent::OnChanged"]
ms.keywords: IPrinterQueueViewEvent interface [Print Devices],OnChanged method, IPrinterQueueViewEvent.OnChanged, IPrinterQueueViewEvent::OnChanged, OnChanged, OnChanged method [Print Devices], OnChanged method [Print Devices],IPrinterQueueViewEvent interface, print.iprinterqueueviewevent_onchanged, printerextension/IPrinterQueueViewEvent::OnChanged
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
 - IPrinterQueueViewEvent::OnChanged
 - printerextension/IPrinterQueueViewEvent::OnChanged
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterQueueViewEvent::OnChanged
---

## -description

Provides an [IPrintJobCollection](./nn-printerextension-iprintjobcollection.md) object that provides a snapshot of a range of print jobs in the queue.

## -parameters

### -param pCollection [in]

An [IPrintJobCollection](./nn-printerextension-iprintjobcollection.md) object.

### -param ulViewOffset [in]

The start of the range of jobs being monitored.

### -param ulViewSize [in]

The range of jobs being monitored.

### -param ulCountJobsInPrintQueue [in]

The current number of jobs in the print queue.

## -returns

This method returns the appropriate **HRESULT** value.

## -remarks

The job range is controlled by the [IPrinterQueueView](./nn-printerextension-iprinterqueueview.md) interface. Additionally, this method provides the current number of jobs in the print queue, and the indices of the job range being monitored. Information about the number of jobs, and the indices of the jobs is provided in response to the [IPrinterQueueView::SetViewRange](./nf-printerextension-iprinterqueueview-setviewrange.md) method being invoked.

## -see-also

[IPrintJobCollection](./nn-printerextension-iprintjobcollection.md)

[IPrinterQueueView](./nn-printerextension-iprinterqueueview.md)

[IPrinterQueueView::SetViewRange](./nf-printerextension-iprinterqueueview-setviewrange.md)

[IPrinterQueueViewEvent](./nn-printerextension-iprinterqueueviewevent.md)