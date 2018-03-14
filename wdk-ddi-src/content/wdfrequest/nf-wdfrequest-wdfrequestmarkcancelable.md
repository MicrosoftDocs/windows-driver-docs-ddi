---
UID: NF:wdfrequest.WdfRequestMarkCancelable
title: WdfRequestMarkCancelable function
author: windows-driver-content
description: The WdfRequestMarkCancelable method enables cancellation of a specified I/O request.
old-location: wdf\wdfrequestmarkcancelable.htm
old-project: wdf
ms.assetid: 1bd1ec2a-8b07-4843-84b6-6b651453328c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_29a4ad0c-ce28-4f4b-b015-90b067feaeec.xml, WdfRequestMarkCancelable, WdfRequestMarkCancelable method, kmdf.wdfrequestmarkcancelable, wdf.wdfrequestmarkcancelable, wdfrequest/WdfRequestMarkCancelable
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
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, EvtIoStopCancel, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, ReqIsCancOnCancReq, ReqMarkCancelableSend, ReqNotCanceledLocal, RequestCompleted, RequestCompletedLocal
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
-	WdfRequestMarkCancelable
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestMarkCancelable function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestMarkCancelable</b> method enables cancellation of a specified I/O request.


## -syntax


````
VOID WdfRequestMarkCancelable(
  _In_ WDFREQUEST             Request,
  _In_ PFN_WDF_REQUEST_CANCEL EvtRequestCancel
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param EvtRequestCancel [in]

A pointer to a driver-defined <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function, which the framework calls if it cancels the I/O request.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



After your driver has <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/receiving-i-o-requests">received an I/O request</a> from the framework, the driver can call <b>WdfRequestMarkCancelable</b> or, starting with  KMDF version 1.9, <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> to make the request cancelable.

When calling <b>WdfRequestMarkCancelable</b>, your driver must specify an <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function. The framework calls the callback function if the I/O manager or another driver is attempting to cancel the I/O request.

<h3><a id="choosing"></a><a id="CHOOSING"></a>Choosing between WdfRequestMarkCancelable and WdfRequestMarkCancelableEx</h3>
If your driver uses the framework's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-automatic-synchronization">automatic synchronization</a>, the driver can call either <b>WdfRequestMarkCancelable</b> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>.

If the driver does not use automatic synchronization, it must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> instead of <b>WdfRequestMarkCancelable</b> for the following reasons:

<ul>
<li>
If the specified request has already been canceled, <b>WdfRequestMarkCancelable</b> calls the driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function before returning. If the driver acquires a spinlock before calling <b>WdfRequestMarkCancelable</b> and attempts to acquire the same spinlock inside  <i>EvtRequestCancel</i>, the same thread attempts to acquire the same spinlock twice, causing a deadlock.

</li>
<li>
However, because <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> never calls <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>, this scenario does not occur. If the request has already been canceled, <b>WdfRequestMarkCancelableEx</b> returns <b>STATUS_CANCELLED</b>. If your driver acquires a spinlock (which sets the IRQL to DISPATCH_LEVEL) before calling <b>WdfRequestMarkCancelableEx</b> and releases the spinlock (which sets the IRQL to PASSIVE_LEVEL) after <b>WdfRequestMarkCancelableEx</b> returns, the <i>EvtRequestCancel</i> callback function will not be called before the spinlock is released. Therefore, a deadlock does not occur even if the <i>EvtRequestCancel</i> callback function uses the same spinlock.

</li>
</ul>
<h3><a id="Processing_a_request_after_enabling_cancellation"></a><a id="processing_a_request_after_enabling_cancellation"></a><a id="PROCESSING_A_REQUEST_AFTER_ENABLING_CANCELLATION"></a>Processing a request after enabling cancellation</h3>
After a driver calls <b>WdfRequestMarkCancelable</b> to enable canceling, the request remains cancelable while the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">owns</a> the request object, unless the driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a>. 

If a driver has called <b>WdfRequestMarkCancelable</b>, and if the driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function has not executed and called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a> before it calls <b>WdfRequestComplete</b> outside of the <i>EvtRequestCancel</i> callback function.

If the driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a> to forward the request to a different queue, the following rules apply:

<ul>
<li>
I/O requests cannot be cancelable when your driver forwards them to a different queue. 

Generally, your driver should not call <b>WdfRequestMarkCancelable</b> to enable canceling the request before calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a>. If the driver does make the request cancelable, it must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a> to disable cancellation before calling <b>WdfRequestForwardToIoQueue</b>.

</li>
<li>
While the request is in the second queue, the framework owns it and can cancel it without notifying the driver.

If the driver requires cancellation notification (so that it can deallocate any resources that it might have allocated before calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a>), the driver should register an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_canceled_on_queue.md">EvtIoCanceledOnQueue</a> callback function, and it should use request-specific context memory to store information about the request's resources.

</li>
<li>
After the framework has dequeued the request from the second queue and delivered it to the driver, the driver can call <b>WdfRequestMarkCancelable</b> to enable canceling.

</li>
</ul>
For more information about <b>WdfRequestMarkCancelable</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.


#### Examples

The following code example shows parts of two callback functions: 

<ul>
<li>
An <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a> callback function that performs request-specific work (such as creating subrequests to send to an I/O target), then enables cancellation of the received I/O request.

</li>
<li>
An <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function that cancels an I/O request.

</li>
</ul>
The driver must use the framework's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-automatic-synchronization">automatic synchronization</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
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
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestMarkCancelable method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

