---
UID: NF:wdfrequest.WdfRequestMarkCancelable
title: WdfRequestMarkCancelable function (wdfrequest.h)
description: The WdfRequestMarkCancelable method enables cancellation of a specified I/O request.
old-location: wdf\wdfrequestmarkcancelable.htm
tech.root: wdf
ms.assetid: 1bd1ec2a-8b07-4843-84b6-6b651453328c
ms.date: 02/26/2018
keywords: ["WdfRequestMarkCancelable function"]
ms.keywords: DFRequestObjectRef_29a4ad0c-ce28-4f4b-b015-90b067feaeec.xml, WdfRequestMarkCancelable, WdfRequestMarkCancelable method, kmdf.wdfrequestmarkcancelable, wdf.wdfrequestmarkcancelable, wdfrequest/WdfRequestMarkCancelable
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, EvtIoStopCancel, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, ReqIsCancOnCancReq, ReqMarkCancelableSend, ReqNotCanceledLocal, RequestCompleted, RequestCompletedLocal
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestMarkCancelable
 - wdfrequest/WdfRequestMarkCancelable
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
 - WdfRequestMarkCancelable
---

# WdfRequestMarkCancelable function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestMarkCancelable</b> method enables cancellation of a specified I/O request.

## -parameters

### -param Request 

[in]
A handle to a framework request object.

### -param EvtRequestCancel 

[in]
A pointer to a driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function, which the framework calls if it cancels the I/O request.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.




After your driver has <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/receiving-i-o-requests">received an I/O request</a> from the framework, the driver can call <b>WdfRequestMarkCancelable</b> or, starting with  KMDF version 1.9, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> to make the request cancelable.

When calling <b>WdfRequestMarkCancelable</b>, your driver must specify an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function. The framework calls the callback function if the I/O manager or another driver is attempting to cancel the I/O request.

<h3><a id="choosing"></a><a id="CHOOSING"></a>Choosing between WdfRequestMarkCancelable and WdfRequestMarkCancelableEx</h3>
If your driver uses the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">automatic synchronization</a>, the driver can call either <b>WdfRequestMarkCancelable</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>.

If the driver does not use automatic synchronization, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> instead of <b>WdfRequestMarkCancelable</b> for the following reasons:

<ul>
<li>
If the specified request has already been canceled, <b>WdfRequestMarkCancelable</b> calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function before returning. If the driver acquires a spinlock before calling <b>WdfRequestMarkCancelable</b> and attempts to acquire the same spinlock inside  <i>EvtRequestCancel</i>, the same thread attempts to acquire the same spinlock twice, causing a deadlock.

</li>
<li>
However, because <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> never calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a>, this scenario does not occur. If the request has already been canceled, <b>WdfRequestMarkCancelableEx</b> returns <b>STATUS_CANCELLED</b>. If your driver acquires a spinlock (which sets the IRQL to DISPATCH_LEVEL) before calling <b>WdfRequestMarkCancelableEx</b> and releases the spinlock (which sets the IRQL to PASSIVE_LEVEL) after <b>WdfRequestMarkCancelableEx</b> returns, the <i>EvtRequestCancel</i> callback function will not be called before the spinlock is released. Therefore, a deadlock does not occur even if the <i>EvtRequestCancel</i> callback function uses the same spinlock.

</li>
</ul>
<h3><a id="Processing_a_request_after_enabling_cancellation"></a><a id="processing_a_request_after_enabling_cancellation"></a><a id="PROCESSING_A_REQUEST_AFTER_ENABLING_CANCELLATION"></a>Processing a request after enabling cancellation</h3>
After a driver calls <b>WdfRequestMarkCancelable</b> to enable canceling, the request remains cancelable while the driver <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-ownership">owns</a> the request object, unless the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>. 

If a driver has called <b>WdfRequestMarkCancelable</b>, and if the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function has not executed and called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> before it calls <b>WdfRequestComplete</b> outside of the <i>EvtRequestCancel</i> callback function.

If the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a> to forward the request to a different queue, the following rules apply:

<ul>
<li>
I/O requests cannot be cancelable when your driver forwards them to a different queue. 

Generally, your driver should not call <b>WdfRequestMarkCancelable</b> to enable canceling the request before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>. If the driver does make the request cancelable, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> to disable cancellation before calling <b>WdfRequestForwardToIoQueue</b>.

</li>
<li>
While the request is in the second queue, the framework owns it and can cancel it without notifying the driver.

If the driver requires cancellation notification (so that it can deallocate any resources that it might have allocated before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>), the driver should register an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_canceled_on_queue">EvtIoCanceledOnQueue</a> callback function, and it should use request-specific context memory to store information about the request's resources.

</li>
<li>
After the framework has dequeued the request from the second queue and delivered it to the driver, the driver can call <b>WdfRequestMarkCancelable</b> to enable canceling.

</li>
</ul>
For more information about <b>WdfRequestMarkCancelable</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.


#### Examples

The following code example shows parts of two callback functions: 

<ul>
<li>
An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a> callback function that performs request-specific work (such as creating subrequests to send to an I/O target), then enables cancellation of the received I/O request.

</li>
<li>
An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function that cancels an I/O request.

</li>
</ul>
The driver must use the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">automatic synchronization</a>.

```cpp
VOID
MyEvtIoRead(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
...
    // Perform request-specific work here
    // (such as creating subrequests 
    // to send to an I/O target). 
...
    WdfRequestMarkCancelable(
                             Request,
                             MyEvtRequestCancel
                             );
    }
...
}
VOID
MyEvtRequestCancel(
    IN WDFREQUEST  Request
    )
{
    // Remove request-specific work here, because
    // we don't want the work to be done if the
    // request was canceled.

    WdfRequestComplete(
                       Request,
                       STATUS_CANCELLED
                       );
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>

