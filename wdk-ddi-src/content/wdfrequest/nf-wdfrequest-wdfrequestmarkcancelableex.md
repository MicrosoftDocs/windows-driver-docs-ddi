---
UID: NF:wdfrequest.WdfRequestMarkCancelableEx
title: WdfRequestMarkCancelableEx function (wdfrequest.h)
description: The WdfRequestMarkCancelableEx method enables cancellation of a specified I/O request.
old-location: wdf\wdfrequestmarkcancelableex.htm
tech.root: wdf
ms.assetid: 5513804b-f785-4617-81b6-1cecc72d6051
ms.date: 02/26/2018
keywords: ["WdfRequestMarkCancelableEx function"]
ms.keywords: DFRequestObjectRef_6601e5df-d8a6-42b5-9e71-a46918a6bc1f.xml, WdfRequestMarkCancelableEx, WdfRequestMarkCancelableEx method, kmdf.wdfrequestmarkcancelableex, wdf.wdfrequestmarkcancelableex, wdfrequest/WdfRequestMarkCancelableEx
f1_keywords:
 - "wdfrequest/WdfRequestMarkCancelableEx"
 - "WdfRequestMarkCancelableEx"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
- WdfRequestMarkCancelableEx
targetos: Windows
req.typenames: 
---

# WdfRequestMarkCancelableEx function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestMarkCancelableEx</b> method enables cancellation of a specified I/O request.


## -parameters




### -param Request 
[in]
A handle to a framework request object.


### -param EvtRequestCancel 
[in]
A pointer to a driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function, which the framework calls if it cancels the I/O request.


## -returns



<b>WdfRequestMarkCancelableEx</b> returns STATUS_SUCCESS if it successfully enables cancellation of the specified I/O request. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The I/O request has been canceled. See Remarks for more info.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
<ul>
<li>
The driver does not own the I/O request.

</li>
<li>
The I/O request is already cancelable.

</li>
</ul>
</td>
</tr>
</table>
 

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



After your driver has <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/receiving-i-o-requests">received an I/O request</a> from the framework, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a> or, starting with  KMDF version 1.9, <b>WdfRequestMarkCancelableEx</b> to make the request cancelable. For info on choosing between the two methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a>.

When calling <b>WdfRequestMarkCancelableEx</b>, your driver must specify an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function. The framework calls the callback function if the I/O manager or another driver is attempting to cancel the I/O request.

If <b>WdfRequestMarkCancelableEx</b> returns failure, the driver must perform the same cancellation activities that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function performs.  For example:

<ol>
<li>
Finish or stop processing the request, along with subrequests that it might have created.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>, specifying a status value of STATUS_CANCELLED.

</li>
</ol>
 See the code examples below for implementation.

Because <b>WdfRequestMarkCancelableEx</b> never calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a>, this method is safe from the deadlock risk described in the Remarks of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a>.

<h3><a id="Processing_a_request_after_enabling_cancellation"></a><a id="processing_a_request_after_enabling_cancellation"></a><a id="PROCESSING_A_REQUEST_AFTER_ENABLING_CANCELLATION"></a>Processing a request after enabling cancellation</h3>
After a driver calls <b>WdfRequestMarkCancelableEx</b> to enable canceling, the request remains cancelable while the driver <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-ownership">owns</a> the request object, unless the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>. 

If a driver has called <b>WdfRequestMarkCancelableEx</b>, and if the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function has not executed and called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> before it calls <b>WdfRequestComplete</b> outside of the <i>EvtRequestCancel</i> callback function.

If the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a> to forward the request to a different queue, the following rules apply:

<ul>
<li>
I/O requests cannot be cancelable when your driver forwards them to a different queue. 

Generally, your driver should not call <b>WdfRequestMarkCancelableEx</b> to enable canceling the request before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>. If the driver does make the request cancelable, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> to disable cancellation before calling <b>WdfRequestForwardToIoQueue</b>.

</li>
<li>
While the request is in the second queue, the framework owns it and can cancel it without notifying the driver. 

If the driver requires cancellation notification (so that it can deallocate any resources that it might have allocated before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>), the driver should register an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_canceled_on_queue">EvtIoCanceledOnQueue</a> callback function, and it should use request-specific context memory to store information about the request's resources.

</li>
<li>
After the framework has dequeued the request from the second queue and delivered it to the driver, the driver can call <b>WdfRequestMarkCancelableEx</b> to enable canceling.

</li>
</ul>
For more information about <b>WdfRequestMarkCancelableEx</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.


#### Examples

The following code examples show parts of two callback functions: 

<ul>
<li>
An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a> callback function that performs request-specific work (such as creating subrequests to send to an I/O target), then enables cancellation of the received I/O request.

</li>
<li>
An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function that cancels an I/O request.

</li>
</ul>
In the first example, the driver is using the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">automatic synchronization</a>. In the second example, the driver is providing its own synchronization by using spinlocks.

<b>Example 1: A driver that uses automatic synchronization.</b>

```cpp
VOID
MyEvtIoRead(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
...
    NTSTATUS status;
...
    // Perform request-specific work here
    // (such as creating subrequests 
    // to send to an I/O target). 
...
    status = WdfRequestMarkCancelableEx(
                                        Request,
                                        MyEvtRequestCancel
                                        );

    if (!NT_SUCCESS(status)) {
       // Remove request-specific work here, because
       // we don't want the work to be done if the
       // request was canceled or an error occurred.

        WdfRequestComplete (Request, status);
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
<b>Example 2: A driver that uses its own synchronization.</b>

```cpp
VOID
MyEvtIoRead(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
...
    NTSTATUS status;
...
    WdfSpinlockAcquire(MyCancelSpinLock);
    // Perform request-specific work here
    // (such as creating subrequests 
    // to send to an I/O target). 
...
    status = WdfRequestMarkCancelableEx(
                                        Request,
                                        MyEvtRequestCancel
                                        );

    if (!NT_SUCCESS(status)) {
        // Remove request-specific work here, because
        // we don't want the work to be done if the
        // request was canceled or an error occurred.
     }
    WdfSpinlockRelease(MyCancelSpinLock);
    if (!NT_SUCCESS(status)) {
        WdfRequestComplete (
                            Request,
                            Status
                            );
    }
...
}
VOID
MyEvtRequestCancel(
    IN WDFREQUEST  Request
 )
{
    WdfSpinlockAcquire(MyCancelSpinLock);
    // Remove request-specific work here, because
    // we don't want the work to be done if the
    // request was canceled.
    WdfSpinlockRelease(MyCancelSpinLock);
    WdfRequestComplete (Request, STATUS_CANCELLED);
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>
 

 

