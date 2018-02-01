---
UID: NF:printerextension.IPrinterQueueViewEvent.OnChanged
title: IPrinterQueueViewEvent::OnChanged method
author: windows-driver-content
description: Provides an IPrintJobCollection object that provides a snapshot of a range of print jobs in the queue.
old-location: print\iprinterqueueviewevent_onchanged.htm
old-project: print
ms.assetid: D964A0C4-041A-47BD-87AB-4AF523939DF0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: OnChanged, IPrinterQueueViewEvent::OnChanged, OnChanged method [Print Devices], printerextension/IPrinterQueueViewEvent::OnChanged, print.iprinterqueueviewevent_onchanged, IPrinterQueueViewEvent, OnChanged method [Print Devices], IPrinterQueueViewEvent interface, IPrinterQueueViewEvent interface [Print Devices], OnChanged method
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrinterQueueViewEvent.OnChanged
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterQueueViewEvent::OnChanged method


## -description


Provides an <a href="..\printerextension\nn-printerextension-iprintjobcollection.md">IPrintJobCollection</a> object that provides a snapshot of a range of print jobs in the queue.


## -syntax


````
HRESULT OnChanged(
  [in] IPrintJobCollection *pCollection,
  [in] ULONG               ulViewOffset,
  [in] ULONG               ulViewSize,
  [in] ULONG               ulCountJobsInPrintQueue
);
````


## -parameters




### -param pCollection [in]

An <a href="..\printerextension\nn-printerextension-iprintjobcollection.md">IPrintJobCollection</a> object.


### -param ulViewOffset [in]

The start of the range of jobs being monitored.


### -param ulViewSize [in]

The range of jobs being monitored.


### -param ulCountJobsInPrintQueue [in]

The current number of jobs in the print queue.


## -returns


This method returns the appropriate <b>HRESULT</b> value.



## -remarks


The job range is controlled by the <a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a> interface. Additionally, this method provides the current number of jobs in the print queue, and the indices of the job range being monitored. Information about the number of jobs, and the indices of the jobs is provided in response to the <a href="https://msdn.microsoft.com/DB3C0439-EB82-4E49-8FEA-003C1B4A9EE0">IPrinterQueueView::SetViewRange</a> method being invoked.



## -see-also

<a href="https://msdn.microsoft.com/DB3C0439-EB82-4E49-8FEA-003C1B4A9EE0">IPrinterQueueView::SetViewRange</a>

<a href="..\printerextension\nn-printerextension-iprinterqueueviewevent.md">IPrinterQueueViewEvent</a>

<a href="..\printerextension\nn-printerextension-iprintjobcollection.md">IPrintJobCollection</a>

<a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueueViewEvent::OnChanged method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

