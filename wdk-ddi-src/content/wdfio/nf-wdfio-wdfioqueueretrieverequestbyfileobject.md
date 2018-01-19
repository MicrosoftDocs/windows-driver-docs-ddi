---
UID: NF:wdfio.WdfIoQueueRetrieveRequestByFileObject
title: WdfIoQueueRetrieveRequestByFileObject function
author: windows-driver-content
description: The WdfIoQueueRetrieveRequestByFileObject method retrieves the next available I/O request, from a specified I/O queue, that is associated with a specified file object.
old-location: wdf\wdfioqueueretrieverequestbyfileobject.htm
old-project: wdf
ms.assetid: 6acff4d8-c21f-49c5-a255-5b46aac97c9f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoQueueRetrieveRequestByFileObject
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
req.alt-api: WdfIoQueueRetrieveRequestByFileObject
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DoubleCompletion, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
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
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The driver supplied an invalid handle.
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>The framework reached the end of the I/O queue.
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>The specified I/O queue is configured for the parallel dispatching method.
<dl>
<dt><b>STATUS_WDF_PAUSED</b></dt>
</dl>The specified I/O queue is <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-power-managed-i-o-queues">power-managed</a> and its device is in a low-power state.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
A driver that has configured an I/O queue for manual or sequential dispatching might call <b>WdfIoQueueRetrieveRequestByFileObject</b>. For more information about using <b>WdfIoQueueRetrieveRequestByFileObject</b> with the manual or sequential dispatching methods, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">Dispatching Methods for I/O Requests</a>. 

After calling <b>WdfIoQueueRetrieveRequestByFileObject</b> to obtain an I/O request, the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">owns</a> the request and must <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">process the I/O request</a> in some manner.

For more information about the <b>WdfIoQueueRetrieveRequestByFileObject</b> method, see <a href="https://msdn.microsoft.com/83cc87c8-7e2d-4f79-a580-0519d327e7ba">Managing I/O Queues</a>.

The following code example obtains, from a specified I/O queue, a handle to the next framework request object that is associated with a specified framework file object.


## -see-also
<dl>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueueretrievefoundrequest.md">WdfIoQueueRetrieveFoundRequest</a>
</dt>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueueretrievenextrequest.md">WdfIoQueueRetrieveNextRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueRetrieveRequestByFileObject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

