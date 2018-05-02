---
UID: NN:printerextension.IPrinterQueue2
title: IPrinterQueue2
author: windows-driver-content
description: Represents a single printer queue.
old-location: print\iprinterqueue2.htm
old-project: print
ms.assetid: 06459A1F-A14B-43BA-9771-47205CC3F388
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrinterQueue2, IPrinterQueue2 interface [Print Devices], IPrinterQueue2 interface [Print Devices],described, print.iprinterqueue2, printerextension/IPrinterQueue2
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
-	IPrinterQueue2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueue2 interface


## -description


Represents a single printer queue. 

This interface extends <a href="https://msdn.microsoft.com/library/windows/hardware/hh439635">IPrinterQueue</a> and allows a user to manage print jobs and device maintenance from within a UWP  device app for printers, or from a printer extension.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterQueue2</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/hh439635">IPrinterQueue</a>. <b>IPrinterQueue2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterQueue2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265390">GetPrinterQueueView</a>
</td>
<td align="left" width="63%">
Retrieves an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265392">IPrinterQueueView</a> object, and initializes the object with the range of jobs to be monitored.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265391">SendBidiSetRequestAsync</a>
</td>
<td align="left" width="63%">
Uses an XML string value to send a Bidi Set request as an asynchronous operation.

</td>
</tr>
</table> 


## -remarks



<b>IPrinterQueue2</b> also helps to make it possible to perform device maintenance and job management from a UWP  device app or from a printer extension. For more information, see <a href="https://msdn.microsoft.com/310E92A9-F751-4346-9B2D-0578A136AD20">Device Maintenance</a> and <a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>.




## -see-also




<a href="https://msdn.microsoft.com/310E92A9-F751-4346-9B2D-0578A136AD20">Device Maintenance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439635">IPrinterQueue</a>



<a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>
 

 

