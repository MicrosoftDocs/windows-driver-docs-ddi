---
UID: NF:wdfio.WdfIoQueueRetrieveRequestByFileObject
title: WdfIoQueueRetrieveRequestByFileObject function
author: windows-driver-content
description: The WdfIoQueueRetrieveRequestByFileObject method retrieves the next available I/O request, from a specified I/O queue, that is associated with a specified file object.
old-location: wdf\wdfioqueueretrieverequestbyfileobject.htm
tech.root: wdf
ms.assetid: 6acff4d8-c21f-49c5-a255-5b46aac97c9f
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_52e014c4-04ca-44b2-a5a8-19185b085cdf.xml, WdfIoQueueRetrieveRequestByFileObject, WdfIoQueueRetrieveRequestByFileObject method, kmdf.wdfioqueueretrieverequestbyfileobject, wdf.wdfioqueueretrieverequestbyfileobject, wdfio/WdfIoQueueRetrieveRequestByFileObject
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DoubleCompletion, DriverCreate, KmdfIrql, KmdfIrql2
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
-	WdfIoQueueRetrieveRequestByFileObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoQueueRetrieveRequestByFileObject function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueueRetrieveRequestByFileObject</b> method retrieves the next available I/O request, from a specified I/O queue, that is associated with a specified file object. 


## -parameters




### -param Queue [in]

A handle to a framework queue object.


### -param FileObject [in]

A handle to a framework file object.


### -param OutRequest [out]

A pointer to a location that receives a handle to a framework request object. If <b>WdfIoQueueRetrieveRequestByFileObject</b> does not return STATUS_SUCCESS, it does not set the location's value. 


## -returns



<b>WdfIoQueueRetrieveRequestByFileObject</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
The specified I/O queue is <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-power-managed-i-o-queues">power-managed</a> and its device is in a low-power state.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver that has configured an I/O queue for manual or sequential dispatching might call <b>WdfIoQueueRetrieveRequestByFileObject</b>. For more information about using <b>WdfIoQueueRetrieveRequestByFileObject</b> with the manual or sequential dispatching methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">Dispatching Methods for I/O Requests</a>. 

After calling <b>WdfIoQueueRetrieveRequestByFileObject</b> to obtain an I/O request, the driver <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-ownership">owns</a> the request and must <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">process the I/O request</a> in some manner.

For more information about the <b>WdfIoQueueRetrieveRequestByFileObject</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example obtains, from a specified I/O queue, a handle to the next framework request object that is associated with a specified framework file object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFREQUEST  request;

status = WdfIoQueueRetrieveRequestByFileObject(
                                               queue,
                                               fileObject,
                                               &amp;request
                                               );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh975099">WdfIoQueueRetrieveFoundRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975100">WdfIoQueueRetrieveNextRequest</a>
 

 

