---
UID: NF:wdfio.WdfIoQueueRetrieveRequestByFileObject
title: WdfIoQueueRetrieveRequestByFileObject function
author: windows-driver-content
description: The WdfIoQueueRetrieveRequestByFileObject method retrieves the next available I/O request, from a specified I/O queue, that is associated with a specified file object.
old-location: wdf\wdfioqueueretrieverequestbyfileobject.htm
old-project: wdf
ms.assetid: 6acff4d8-c21f-49c5-a255-5b46aac97c9f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFQueueObjectRef_52e014c4-04ca-44b2-a5a8-19185b085cdf.xml, WdfIoQueueRetrieveRequestByFileObject, wdfio/WdfIoQueueRetrieveRequestByFileObject, kmdf.wdfioqueueretrieverequestbyfileobject, wdf.wdfioqueueretrieverequestbyfileobject, WdfIoQueueRetrieveRequestByFileObject method
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfIoQueueRetrieveRequestByFileObject
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueueRetrieveRequestByFileObject function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueRetrieveRequestByFileObject</b> method retrieves the next available I/O request, from a specified I/O queue, that is associated with a specified file object. 


## -syntax


````
NTSTATUS WdfIoQueueRetrieveRequestByFileObject(
  _In_  WDFQUEUE      Queue,
  _In_  WDFFILEOBJECT FileObject,
  _Out_ WDFREQUEST    *OutRequest
);
````


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
The specified I/O queue is <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-power-managed-i-o-queues">power-managed</a> and its device is in a low-power state.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver that has configured an I/O queue for manual or sequential dispatching might call <b>WdfIoQueueRetrieveRequestByFileObject</b>. For more information about using <b>WdfIoQueueRetrieveRequestByFileObject</b> with the manual or sequential dispatching methods, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">Dispatching Methods for I/O Requests</a>. 

After calling <b>WdfIoQueueRetrieveRequestByFileObject</b> to obtain an I/O request, the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">owns</a> the request and must <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">process the I/O request</a> in some manner.

For more information about the <b>WdfIoQueueRetrieveRequestByFileObject</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


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

<a href="..\wdfio\nf-wdfio-wdfioqueueretrievenextrequest.md">WdfIoQueueRetrieveNextRequest</a>



<a href="..\wdfio\nf-wdfio-wdfioqueueretrievefoundrequest.md">WdfIoQueueRetrieveFoundRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueRetrieveRequestByFileObject method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

