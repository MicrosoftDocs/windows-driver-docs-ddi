---
UID: NF:printerextension.IPrinterQueue2.GetPrinterQueueView
title: IPrinterQueue2::GetPrinterQueueView
author: windows-driver-content
description: Retrieves an IPrinterQueueView object, and initializes the object with the range of jobs to be monitored.
old-location: print\iprinterqueue2_getprinterqueueview.htm
old-project: print
ms.assetid: C565288C-B014-4A92-9F50-1641EAA30D22
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: GetPrinterQueueView, GetPrinterQueueView method [Print Devices], GetPrinterQueueView method [Print Devices],IPrinterQueue2 interface, IPrinterQueue2 interface [Print Devices],GetPrinterQueueView method, IPrinterQueue2.GetPrinterQueueView, IPrinterQueue2::GetPrinterQueueView, print.iprinterqueue2_getprinterqueueview, printerextension/IPrinterQueue2::GetPrinterQueueView
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
-	IPrinterQueue2.GetPrinterQueueView
product: Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueue2::GetPrinterQueueView


## -description


Retrieves an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265392">IPrinterQueueView</a> object, and initializes the object with the range of jobs to be monitored.

This method allows the user to perform job management tasks from within a UWP  device app for printers.


## -parameters




### -param ulViewOffset [in]

Indicates the start of the range of jobs to be monitored.


### -param ulViewSize [in]

Indicates the size or the range of jobs to be monitored.


### -param ppJobView [out, retval]

IPrinterQueueView object that shows the range of jobs to be monitored.


## -returns



If the method call is successful, <b>GetPrinterQueueView</b> returns S_OK.

Otherwise, if a call to <b>GetPrinterQueueView</b> results in an error condition, then one of the following <b>HRESULT</b> values can be returned.
	  <table>
<tr>
<th>HRESULT value</th>
<th>Description</th>
</tr>
<tr>
<td>E_ILLEGAL_METHOD_CALL</td>
<td>Indicates an attempt to retrieve more than one printer queue view object.</td>
</tr>
<tr>
<td>E_INVALIDARG</td>
<td>Indicates an attempt to create a view size larger than the maximum size.</td>
</tr>
</table>
 






## -remarks



Only one <a href="https://msdn.microsoft.com/library/windows/hardware/dn265392">IPrinterQueueView</a> object can be retrieved per <a href="https://msdn.microsoft.com/library/windows/hardware/dn265389">IPrinterQueue2</a> object.
However it is possible to move around the single view that you retrieve. In other words, it is possible to  change the positions of the monitored jobs by invoking <a href="https://msdn.microsoft.com/DB3C0439-EB82-4E49-8FEA-003C1B4A9EE0">IPrinterQueueView::SetViewRange</a>.

<div class="alert"><b>Note</b>  There is work underway to implement a cap on the maximum size of the printer queue view.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265389">IPrinterQueue2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265392">IPrinterQueueView</a>
 

 

