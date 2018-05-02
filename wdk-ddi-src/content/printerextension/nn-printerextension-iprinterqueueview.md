---
UID: NN:printerextension.IPrinterQueueView
title: IPrinterQueueView
author: windows-driver-content
description: Provides a way to change the range of print jobs being monitored.
old-location: print\iprinterqueueview.htm
old-project: print
ms.assetid: 81B3D4A3-7176-4656-B23D-04F0F84D9000
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrinterQueueView, IPrinterQueueView interface [Print Devices], IPrinterQueueView interface [Print Devices],described, print.iprinterqueueview, printerextension/IPrinterQueueView
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterQueueView
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueueView interface


## -description


Provides a way to change the range of print jobs being monitored.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterQueueView</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrinterQueueView</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterQueueView</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265395">SetViewRange</a>
</td>
<td align="left" width="63%">
Sets the range of print jobs being monitored.

</td>
</tr>
</table> 


## -remarks



An event is raised whenever the status of the print queue changes. So when a client uses <a href="https://msdn.microsoft.com/library/windows/hardware/dn265395">SetViewRange</a> to specify the range of print jobs (the view) to be monitored, the <a href="https://msdn.microsoft.com/D964A0C4-041A-47BD-87AB-4AF523939DF0">IPrinterQueueViewEvent::OnChanged</a> event method fires, and the live queue is returned in response.

And also, note that job enumeration starts when the first event handler is added and stops when the last event handler is removed.

<b>IPrinterQueueView</b> also helps to make it possible to perform job management from a UWP  device app or from a printer extension. For more information, see <a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>.




## -see-also




<a href="https://msdn.microsoft.com/D964A0C4-041A-47BD-87AB-4AF523939DF0">IPrinterQueueViewEvent::OnChanged</a>



<a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>
 

 

