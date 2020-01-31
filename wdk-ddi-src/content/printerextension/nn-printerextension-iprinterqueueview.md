---
UID: NN:printerextension.IPrinterQueueView
title: IPrinterQueueView (printerextension.h)
description: Provides a way to change the range of print jobs being monitored.
old-location: print\iprinterqueueview.htm
tech.root: print
ms.assetid: 81B3D4A3-7176-4656-B23D-04F0F84D9000
ms.date: 04/20/2018
ms.keywords: IPrinterQueueView, IPrinterQueueView interface [Print Devices], IPrinterQueueView interface [Print Devices],described, print.iprinterqueueview, printerextension/IPrinterQueueView
f1_keywords:
 - "printerextension/IPrinterQueueView"
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrinterQueueView
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueueView interface

## -description

Provides a way to change the range of print jobs being monitored.

## -inheritance

## -remarks

An event is raised whenever the status of the print queue changes. So when a client uses [SetViewRange](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueueview-setviewrange) to specify the range of print jobs (the view) to be monitored, the [IPrinterQueueViewEvent::OnChanged](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueueviewevent-onchanged) event method fires, and the live queue is returned in response.

Note that job enumeration starts when the first event handler is added and stops when the last event handler is removed.

**IPrinterQueueView** also helps to make it possible to perform job management from a UWP device app or from a printer extension. For more information, see [Job Management](https://docs.microsoft.com/windows-hardware/drivers/print/job-management).

## -see-also

[IPrinterQueueViewEvent::OnChanged](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueueviewevent-onchanged)

 [Job Management](https://docs.microsoft.com/windows-hardware/drivers/print/job-management)
