---
UID: NF:wdfio.WdfIoQueueRetrieveNextRequest
title: WdfIoQueueRetrieveNextRequest function (wdfio.h)
description: The WdfIoQueueRetrieveNextRequest method retrieves the next available I/O request from a specified I/O queue.
old-location: wdf\wdfioqueueretrievenextrequest.htm
tech.root: wdf
ms.assetid: 1cde2e20-5ce6-4c5b-b40c-0b04da76980c
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_93fbecf2-1bfa-426c-9739-153d79d0ac27.xml, WdfIoQueueRetrieveNextRequest, WdfIoQueueRetrieveNextRequest method, kmdf.wdfioqueueretrievenextrequest, wdf.wdfioqueueretrievenextrequest, wdfio/WdfIoQueueRetrieveNextRequest
ms.topic: function
f1_keywords:
 - "wdfio/WdfIoQueueRetrieveNextRequest"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfIoQueueRetrieveNextRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoQueueRetrieveNextRequest function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

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
The specified I/O queue is <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-power-managed-i-o-queues">power-managed</a> and its device is in a low-power state, or the specified queue is stopped.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If a driver configures an I/O queue for manual dispatching of I/O requests, the driver typically calls <b>WdfIoQueueRetrieveNextRequest</b> to obtain requests from the queue. A driver that has configured an I/O queue for sequential dispatching might also call <b>WdfIoQueueRetrieveNextRequest</b>. For more information about using <b>WdfIoQueueRetrieveNextRequest</b> with the manual or sequential dispatching methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">Dispatching Methods for I/O Requests</a>. 

After calling <b>WdfIoQueueRetrieveNextRequest</b> to obtain an I/O request, the driver <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-ownership">owns</a> the request and must <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">process the I/O request</a> in some manner.

For more information about the <b>WdfIoQueueRetrieveNextRequest</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


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
                                       pDeviceContext->ReadQueue,
                                       &request
                                       );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/kmdf-wdfioqueueretrievefoundrequest">WdfIoQueueRetrieveFoundRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueueretrieverequestbyfileobject">WdfIoQueueRetrieveRequestByFileObject</a>
 

 

