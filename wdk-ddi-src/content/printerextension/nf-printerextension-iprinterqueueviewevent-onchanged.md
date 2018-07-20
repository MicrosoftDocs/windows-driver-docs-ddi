---
UID: NF:printerextension.IPrinterQueueViewEvent.OnChanged
title: IPrinterQueueViewEvent::OnChanged
author: windows-driver-content
description: Provides an IPrintJobCollection object that provides a snapshot of a range of print jobs in the queue.
old-location: print\iprinterqueueviewevent_onchanged.htm
tech.root: print
ms.assetid: D964A0C4-041A-47BD-87AB-4AF523939DF0
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrinterQueueViewEvent interface [Print Devices],OnChanged method, IPrinterQueueViewEvent.OnChanged, IPrinterQueueViewEvent::OnChanged, OnChanged, OnChanged method [Print Devices], OnChanged method [Print Devices],IPrinterQueueViewEvent interface, print.iprinterqueueviewevent_onchanged, printerextension/IPrinterQueueViewEvent::OnChanged
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterQueueViewEvent.OnChanged
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueueViewEvent::OnChanged


## -description


Provides an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265397">IPrintJobCollection</a> object that provides a snapshot of a range of print jobs in the queue.


## -parameters




### -param pCollection [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/dn265397">IPrintJobCollection</a> object.


### -param ulViewOffset [in]

The start of the range of jobs being monitored.


### -param ulViewSize [in]

The range of jobs being monitored.


### -param ulCountJobsInPrintQueue [in]

The current number of jobs in the print queue.


## -returns



This method returns the appropriate <b>HRESULT</b> value.




## -remarks



The job range is controlled by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265392">IPrinterQueueView</a> interface. Additionally, this method provides the current number of jobs in the print queue, and the indices of the job range being monitored. Information about the number of jobs, and the indices of the jobs is provided in response to the <a href="https://msdn.microsoft.com/DB3C0439-EB82-4E49-8FEA-003C1B4A9EE0">IPrinterQueueView::SetViewRange</a> method being invoked.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265397">IPrintJobCollection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265392">IPrinterQueueView</a>



<a href="https://msdn.microsoft.com/DB3C0439-EB82-4E49-8FEA-003C1B4A9EE0">IPrinterQueueView::SetViewRange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265393">IPrinterQueueViewEvent</a>
 

 

