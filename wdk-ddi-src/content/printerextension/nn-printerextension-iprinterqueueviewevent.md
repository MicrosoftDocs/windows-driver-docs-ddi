---
UID: NN:printerextension.IPrinterQueueViewEvent
title: IPrinterQueueViewEvent (printerextension.h)
description: Provides the signature of the event handler.
old-location: print\iprinterqueueviewevent.htm
tech.root: print
ms.assetid: 23951787-C147-43A6-99D6-71AC037F6A43
ms.date: 04/20/2018
ms.keywords: IPrinterQueueViewEvent, IPrinterQueueViewEvent interface [Print Devices], IPrinterQueueViewEvent interface [Print Devices],described, print.iprinterqueueviewevent, printerextension/IPrinterQueueViewEvent
ms.topic: interface
f1_keywords:
 - "printerextension/IPrinterQueueViewEvent"
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
- IPrinterQueueViewEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueueViewEvent interface


## -description


Provides the signature of the event handler.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterQueueViewEvent</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrinterQueueViewEvent</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterQueueViewEvent</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterqueueviewevent-onchanged">OnChanged</a>
</td>
<td align="left" width="63%">
Provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintjobcollection">IPrintJobCollection</a> object that provides a snapshot of a range of print jobs in the queue.

</td>
</tr>
</table> 


## -remarks



<b>IPrinterQueueViewEvent</b> also helps to make it possible to perform job management from a UWP device app or from a printer extension. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/job-management">Job Management</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/print/job-management">Job Management</a>
 

 

