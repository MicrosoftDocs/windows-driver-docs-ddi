---
UID: NF:printerextension.IPrinterQueueView.SetViewRange
title: IPrinterQueueView::SetViewRange (printerextension.h)
description: Sets the range of print jobs being monitored.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterQueueView::SetViewRange"]
ms.keywords: IPrinterQueueView interface [Print Devices],SetViewRange method, IPrinterQueueView.SetViewRange, IPrinterQueueView::SetViewRange, SetViewRange, SetViewRange method [Print Devices], SetViewRange method [Print Devices],IPrinterQueueView interface, print.iprinterqueueview_setviewrange, printerextension/IPrinterQueueView::SetViewRange
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
 - IPrinterQueueView::SetViewRange
 - printerextension/IPrinterQueueView::SetViewRange
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterQueueView::SetViewRange
---

## -description

Sets the range of print jobs being monitored.

## -parameters

### -param ulViewOffset [in]

The start of the range of jobs being monitored. Note that the offset value uses a zero-based index.

### -param ulViewSize [in]

The  size of the range of jobs being monitored.

## -returns

This method returns the appropriate **HRESULT** value.

## -remarks

Invoking this method causes the events for status change to the jobs to be fired. The [IPrinterQueueViewEvent::OnChanged](./nf-printerextension-iprinterqueueviewevent-onchanged.md) event method returns the live queue in response, using the specified maximum range size.

> [!NOTE]
> *ulViewSize* must be specified as a value less than or equal to 25. If the caller specifies a size which exceeds 25,  this method will return E_INVALIDARG.

## -see-also

[IPrinterQueue2::GetPrinterQueueView](./nf-printerextension-iprinterqueue2-getprinterqueueview.md)

[IPrinterQueueView](./nn-printerextension-iprinterqueueview.md)

[IPrinterQueueViewEvent::OnChanged](./nf-printerextension-iprinterqueueviewevent-onchanged.md)