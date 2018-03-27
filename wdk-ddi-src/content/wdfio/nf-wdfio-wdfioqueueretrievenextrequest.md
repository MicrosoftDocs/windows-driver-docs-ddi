---
UID: NF:wdfio.WdfIoQueueRetrieveNextRequest
title: WdfIoQueueRetrieveNextRequest function
author: windows-driver-content
description: The WdfIoQueueRetrieveNextRequest method retrieves the next available I/O request from a specified I/O queue.
old-location: wdf\wdfioqueueretrievenextrequest.htm
old-project: wdf
ms.assetid: 1cde2e20-5ce6-4c5b-b40c-0b04da76980c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_93fbecf2-1bfa-426c-9739-153d79d0ac27.xml, WdfIoQueueRetrieveNextRequest, WdfIoQueueRetrieveNextRequest method, kmdf.wdfioqueueretrievenextrequest, wdf.wdfioqueueretrievenextrequest, wdfio/WdfIoQueueRetrieveNextRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DoubleCompletion, DriverCreate, KmdfIrql, KmdfIrql2, wdfioqueueretrievenextrequest
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfIoQueueRetrieveNextRequest
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueueRetrieveNextRequest function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueRetrieveNextRequest</b> method retrieves the next available I/O request from a specified I/O queue. 


## -parameters




### -param Queue [in]

A handle to a framework queue object.


### -param OutRequest [out]

A pointer to a location that receives a handle to a framework request object. If the queue is empty or the last request has been retrieved, this parameter receives <b>NULL</b>.


## -returns



<b>WdfIoQueueRetrieveNextRequest</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The driver supplied an invalid handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
The framework reached the end of the I/O queue.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The specified I/O queue is configured for the parallel dispatching method.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_PAUSED</b></dt>
</dl>
</td>
<td width="60%">
The specified I/O queue is <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-power-managed-i-o-queues">power-managed</a> and its device is in a low-power state, or the specified queue is stopped.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If a driver configures an I/O queue for manual dispatching of I/O requests, the driver typically calls <b>WdfIoQueueRetrieveNextRequest</b> to obtain requests from the queue. A driver that has configured an I/O queue for sequential dispatching might also call <b>WdfIoQueueRetrieveNextRequest</b>. For more information about using <b>WdfIoQueueRetrieveNextRequest</b> with the manual or sequential dispatching methods, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">Dispatching Methods for I/O Requests</a>. 

After calling <b>WdfIoQueueRetrieveNextRequest</b> to obtain an I/O request, the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">owns</a> the request and must <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">process the I/O request</a> in some manner.

For more information about the <b>WdfIoQueueRetrieveNextRequest</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example obtains a handle to the next request object that is contained in a device's I/O queue.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;
WDFREQUEST  request;

status = WdfIoQueueRetrieveNextRequest(
                                       pDeviceContext-&gt;ReadQueue,
                                       &amp;request
                                       );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh975099">WdfIoQueueRetrieveFoundRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548470">WdfIoQueueRetrieveRequestByFileObject</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueRetrieveNextRequest method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

