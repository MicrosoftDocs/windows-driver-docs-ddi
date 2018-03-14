---
UID: NF:printerextension.IPrinterQueueView.SetViewRange
title: IPrinterQueueView::SetViewRange method
author: windows-driver-content
description: Sets the range of print jobs being monitored.
old-location: print\iprinterqueueview_setviewrange.htm
old-project: print
ms.assetid: DB3C0439-EB82-4E49-8FEA-003C1B4A9EE0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterQueueView, IPrinterQueueView interface [Print Devices], SetViewRange method, IPrinterQueueView::SetViewRange, SetViewRange method [Print Devices], SetViewRange method [Print Devices], IPrinterQueueView interface, SetViewRange,IPrinterQueueView.SetViewRange, print.iprinterqueueview_setviewrange, printerextension/IPrinterQueueView::SetViewRange
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
-	IPrinterQueueView.SetViewRange
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterQueueView::SetViewRange method


## -description


Sets the range of print jobs being monitored.


## -syntax


````
HRESULT SetViewRange(
  [in] ULONG ulViewOffset,
  [in] ULONG ulViewSize
);
````


## -parameters




### -param ulViewOffset [in]

The start of the range of jobs being monitored. Note that the offset value uses a zero-based index.


### -param ulViewSize [in]

The  size of the range of jobs being monitored.


## -returns



This method returns the appropriate <b>HRESULT</b> value.




## -remarks



Invoking this method causes the events for status change to the jobs to be fired. The <a href="https://msdn.microsoft.com/D964A0C4-041A-47BD-87AB-4AF523939DF0">IPrinterQueueViewEvent::OnChanged</a> event method returns the live queue in response, using the specified maximum range size.

<div class="alert"><b>Note</b>  <i>ulViewSize</i> must be specified as a value less than or equal to 25. If the caller specifies a size which exceeds 25,  this method will return E_INVALIDARG.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/D964A0C4-041A-47BD-87AB-4AF523939DF0">IPrinterQueueViewEvent::OnChanged</a>



<a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a>



<a href="https://msdn.microsoft.com/C565288C-B014-4A92-9F50-1641EAA30D22">IPrinterQueue2::GetPrinterQueueView</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueueView::SetViewRange method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

