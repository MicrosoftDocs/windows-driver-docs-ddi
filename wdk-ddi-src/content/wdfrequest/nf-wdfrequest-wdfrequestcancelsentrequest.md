---
UID: NF:wdfrequest.WdfRequestCancelSentRequest
title: WdfRequestCancelSentRequest function
author: windows-driver-content
description: The WdfRequestCancelSentRequest method attempts to cancel an I/O request that the caller previously submitted to an I/O target.
old-location: wdf\wdfrequestcancelsentrequest.htm
old-project: wdf
ms.assetid: 24319054-5e5c-4330-86e5-b1527c48eaf2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFREQUESTCANCELSENTREQUEST, WdfRequestCancelSentRequest, WdfRequestCancelSentRequest method, kmdf.wdfrequestcancelsentrequest, wdf.wdfrequestcancelsentrequest, DFRequestObjectRef_203c9cb4-5e9d-4a6b-b30d-b60b8eadf6db.xml, wdfrequest/WdfRequestCancelSentRequest
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
req.ddi-compliance: DriverCreate, EvtIoStopCancel, EvtIoStopCompleteOrStopAck, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
-	WdfRequestCancelSentRequest
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestCancelSentRequest function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestCancelSentRequest</b> method attempts to cancel an I/O request that the caller previously submitted to an I/O target.


## -syntax


````
BOOLEAN WdfRequestCancelSentRequest(
  _In_ WDFREQUEST Request
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestCancelSentRequest</b> returns <b>TRUE</b> if it successfully delivers the cancel request to the driver's I/O target. This method returns <b>FALSE</b> if the request has already been completed or canceled, or if the I/O target driver has not called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver can call <b>WdfRequestCancelSentRequest</b> to attempt to cancel an I/O request that it previously had sent to an I/O target by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>.

If the request is in the I/O target's queue, the framework cancels the request. If the framework has already delivered the request to the I/O target's driver, and if that driver has called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> to enable canceling, the framework calls that driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function. If the target's driver has not called <b>WdfRequestMarkCancelable</b> or <b>WdfRequestMarkCancelableEx</b>, the request is not canceled unless the request becomes cancelable.

If the driver has registered a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function for the request, the framework calls the callback function after the request has been canceled.

Typically, if your driver calls <b>WdfRequestCancelSentRequest</b>, it must increment the request object's reference count. For more information, see <a href="https://msdn.microsoft.com/e7ec65c9-bc7b-46ea-853d-3e23b1763666">Synchronizing Cancellation of Sent Requests</a>.

For more information about request cancellation, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.


#### Examples

The following code example is from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256131">kmdf_fx2</a> sample driver. This example is an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function. Because this driver sends each request to its I/O target, the <i>EvtIoStop</i> callback function calls <b>WdfRequestCancelSentRequest</b> if the device has been removed.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
OsrFxEvtIoStop(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN ULONG  ActionFlags
    )
{
    UNREFERENCED_PARAMETER(Queue);

    if (ActionFlags &amp; WdfRequestStopActionSuspend) {
        WdfRequestStopAcknowledge(Request, FALSE);
    } else if (ActionFlags &amp; WdfRequestStopActionPurge) {
        WdfRequestCancelSentRequest(Request);
    }
    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a>



<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>



<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestCancelSentRequest method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

