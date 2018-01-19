---
UID: NF:wdfrequest.WdfRequestForwardToIoQueue
title: WdfRequestForwardToIoQueue function
author: windows-driver-content
description: The WdfRequestForwardToIoQueue method requeues an I/O request to one of the calling driver's I/O queues.
old-location: wdf\wdfrequestforwardtoioqueue.htm
old-project: wdf
ms.assetid: a98d7e74-8311-46bf-a0b9-a160f5675c3d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestForwardToIoQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRequestForwardToIoQueue
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, RequestCompleted, RequestCompletedLocal
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestForwardToIoQueue function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestForwardToIoQueue</b> method requeues an I/O request to one of the calling driver's I/O queues.



## -syntax

````
NTSTATUS WdfRequestForwardToIoQueue(
  _In_ WDFREQUEST Request,
  _In_ WDFQUEUE   DestinationQueue
);
````


## -parameters

### -param Request [in]

A handle to a framework request object.


### -param DestinationQueue [in]

A handle to a framework queue object.


## -returns
<b>WdfRequestForwardToIoQueue</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>This value is returned if one of the following occurs:

The driver did not obtain the request from an I/O queue.

The source and destination queues are the same.

The source and destination queues do not belong to the same device.

The driver does not own the request.

The request is cancelable.
<dl>
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>The destination queue is not accepting new requests.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.




## -remarks
The driver must <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">own</a> the I/O request and must have obtained the request from one of its I/O queues.

The source and destination queues cannot be the same. In other words, the driver cannot call <b>WdfRequestForwardToIoQueue</b> to return a request to the queue that it came from. To requeue a request to the same queue, use <a href="..\wdfrequest\nf-wdfrequest-wdfrequestrequeue.md">WdfRequestRequeue</a>.

Both the source and destination queues must belong to the same device.

The request must not be cancelable. If the driver has called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> to make the request cancelable, it must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a> before calling <b>WdfRequestForwardToIoQueue</b>.

After the driver calls <b>WdfRequestForwardToIoQueue</b>, the driver does not own the requeued request until the framework delivers the request from the new queue to the driver. While the request is in the new queue, the framework owns the request and can cancel it without notifying the driver. 

Before <b>WdfRequestForwardToIoQueue</b> returns, the following events can occur:

If the destination queue was empty, the framework can deliver the requeued I/O request to one of the destination queue's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handlers</a>.

If the source queue's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">dispatching method</a> is sequential or parallel, the framework can deliver another request to one of the source queue's request handlers.

For more information about <b>WdfRequestForwardToIoQueue</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/requeuing-i-o-requests">Requeuing I/O Requests</a> and <a href="https://msdn.microsoft.com/83cc87c8-7e2d-4f79-a580-0519d327e7ba">Managing I/O Queues</a>.

The following code example is an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_device_control.md">EvtIoDeviceControl</a> callback function from the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">PCIDRV</a> sample driver. If a received request contains an I/O control code of IOCTL_NDISPROT_INDICATE_STATUS, the driver calls <b>WdfRequestForwardToIoQueue</b> to move the request to a different I/O queue. 


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestrequeue.md">WdfRequestRequeue</a>
</dt>
<dt>
<a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestForwardToIoQueue method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

