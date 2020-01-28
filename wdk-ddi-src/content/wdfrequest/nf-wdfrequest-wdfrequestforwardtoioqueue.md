---
UID: NF:wdfrequest.WdfRequestForwardToIoQueue
title: WdfRequestForwardToIoQueue function (wdfrequest.h)
description: The WdfRequestForwardToIoQueue method requeues an I/O request to one of the calling driver's I/O queues.
old-location: wdf\wdfrequestforwardtoioqueue.htm
tech.root: wdf
ms.assetid: a98d7e74-8311-46bf-a0b9-a160f5675c3d
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_91c731d6-de15-4ae6-a0d0-ae449a5a47b6.xml, WdfRequestForwardToIoQueue, WdfRequestForwardToIoQueue method, kmdf.wdfrequestforwardtoioqueue, wdf.wdfrequestforwardtoioqueue, wdfrequest/WdfRequestForwardToIoQueue
f1_keywords:
 - "wdfrequest/WdfRequestForwardToIoQueue"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- WdfRequestForwardToIoQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestForwardToIoQueue function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestForwardToIoQueue</b> method requeues an I/O request to one of the calling driver's I/O queues.


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param DestinationQueue [in]

A handle to a framework queue object.


## -returns



<b>WdfRequestForwardToIoQueue</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
This value is returned if one of the following occurs:

<ul>
<li>
The driver did not obtain the request from an I/O queue.

</li>
<li>
The source and destination queues are the same.

</li>
<li>
The source and destination queues do not belong to the same device.

</li>
<li>
The driver does not own the request.

</li>
<li>
The request is cancelable.

</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The destination queue is not accepting new requests.

</td>
</tr>
</table>
 

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The driver must <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-ownership">own</a> the I/O request and must have obtained the request from one of its I/O queues.

The source and destination queues cannot be the same. In other words, the driver cannot call <b>WdfRequestForwardToIoQueue</b> to return a request to the queue that it came from. To requeue a request to the same queue, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestrequeue">WdfRequestRequeue</a>.

Both the source and destination queues must belong to the same device.

The request must not be cancelable. If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> to make the request cancelable, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> before calling <b>WdfRequestForwardToIoQueue</b>.

After the driver calls <b>WdfRequestForwardToIoQueue</b>, the driver does not own the requeued request until the framework delivers the request from the new queue to the driver. While the request is in the new queue, the framework owns the request and can cancel it without notifying the driver. 

Before <b>WdfRequestForwardToIoQueue</b> returns, the following events can occur:

<ul>
<li>
If the destination queue was empty, the framework can deliver the requeued I/O request to one of the destination queue's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handlers</a>.

</li>
<li>
If the source queue's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">dispatching method</a> is sequential or parallel, the framework can deliver another request to one of the source queue's request handlers.

</li>
</ul>
For more information about <b>WdfRequestForwardToIoQueue</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/requeuing-i-o-requests">Requeuing I/O Requests</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_device_control">EvtIoDeviceControl</a> callback function from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">PCIDRV</a> sample driver. If a received request contains an I/O control code of IOCTL_NDISPROT_INDICATE_STATUS, the driver calls <b>WdfRequestForwardToIoQueue</b> to move the request to a different I/O queue. 

```cpp
VOID
PciDrvEvtIoDeviceControl(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  OutputBufferLength,
    IN size_t  InputBufferLength,
    IN ULONG  IoControlCode
    )
{
    NTSTATUS  status= STATUS_SUCCESS;
    PFDO_DATA  fdoData = NULL;
    WDFDEVICE  hDevice;
    WDF_REQUEST_PARAMETERS  params;

    UNREFERENCED_PARAMETER(OutputBufferLength);
    UNREFERENCED_PARAMETER(InputBufferLength);

    hDevice = WdfIoQueueGetDevice(Queue);
    fdoData = FdoGetData(hDevice);

    WDF_REQUEST_PARAMETERS_INIT(&params);
    WdfRequestGetParameters(
                            Request,
                            &params
                            );

    switch (IoControlCode)
    {
        case IOCTL_NDISPROT_QUERY_OID_VALUE:
            NICHandleQueryOidRequest(
                                     Queue,
                                     Request,
                                     &params
                                     );
            break;

        case IOCTL_NDISPROT_SET_OID_VALUE:
            NICHandleSetOidRequest(
                                   Queue,
                                   Request,
                                   &params
                                   );
            break;

        case IOCTL_NDISPROT_INDICATE_STATUS:
            status = WdfRequestForwardToIoQueue(
                                                Request,
                                                fdoData->PendingIoctlQueue
                                                );
            if(!NT_SUCCESS(status)){
                WdfRequestComplete(
                                   Request,
                                   status
                                   );
                break;
            }
            break;

        default:
            WdfRequestComplete(
                               Request,
                               STATUS_INVALID_DEVICE_REQUEST
                               );
            break;
    }
    return;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestrequeue">WdfRequestRequeue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>
 

 

