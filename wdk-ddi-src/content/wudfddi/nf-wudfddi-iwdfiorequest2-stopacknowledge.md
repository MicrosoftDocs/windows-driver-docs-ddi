---
UID: NF:wudfddi.IWDFIoRequest2.StopAcknowledge
title: IWDFIoRequest2::StopAcknowledge (wudfddi.h)
description: The StopAcknowledge method informs the framework that the driver has stopped processing a specified I/O request.
old-location: wdf\iwdfiorequest2_stopacknowledge.htm
tech.root: wdf
ms.assetid: af4ae2c0-b1e1-45af-bd0e-3b9a91566caa
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest2 interface,StopAcknowledge method, IWDFIoRequest2.StopAcknowledge, IWDFIoRequest2::StopAcknowledge, StopAcknowledge, StopAcknowledge method, StopAcknowledge method,IWDFIoRequest2 interface, UMDFRequestObjectRef_9a125e95-f59a-4338-a7af-cb7f99289eb7.xml, umdf.iwdfiorequest2_stopacknowledge, wdf.iwdfiorequest2_stopacknowledge, wudfddi/IWDFIoRequest2::StopAcknowledge
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoRequest2.StopAcknowledge
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest2::StopAcknowledge


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>StopAcknowledge</b> method informs the framework that the driver has stopped processing a specified I/O request.


## -parameters




### -param Requeue [in]

A Boolean value that, if <b>TRUE</b>, causes the framework to requeue the request into the queue so that the framework will deliver it to the driver again. If <b>FALSE</b>, the framework does not requeue the request. For more information, see the following Remarks section.


## -returns



None.




## -remarks



If a driver registers an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackiostop-oniostop">IQueueCallbackIoStop::OnIoStop</a> callback function for an I/O queue, the framework calls it when the queue's underlying device is leaving its working (D0) state. The framework calls this callback function for every I/O request that the driver owns at the time when the queue is being stopped. The driver must complete, cancel, or postpone processing of each request by doing one of the following: 

<ul>
<li>
If the driver owns the request, it can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a> to complete or cancel the request.

</li>
<li>
If the driver has forwarded the request to an I/O target, it can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-cancelsentrequest">IWDFIoRequest::CancelSentRequest</a> to attempt to cancel the request.

</li>
<li>
If the driver postpones processing the request, it must call <b>StopAcknowledge</b>.

</li>
</ul>
If your driver calls <b>StopAcknowledge</b>, it must call this method from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackiostop-oniostop">IQueueCallbackIoStop::OnIoStop</a> callback function.

If the driver does not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a> or <b>StopAcknowledge</b> for every request that an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackiostop-oniostop">IQueueCallbackIoStop::OnIoStop</a> callback function receives, the framework does not allow the device to leave its working (D0) state. Potentially, this inaction can prevent a system from entering its hibernation state or another low system power state. 

When a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackiostop-oniostop">IQueueCallbackIoStop::OnIoStop</a> callback function calls <b>StopAcknowledge</b>, it can set the <i>Requeue</i> parameter to <b>TRUE</b> or <b>FALSE</b>: 

<ul>
<li>
Setting <i>Requeue</i> to <b>TRUE</b> causes the framework to place the request back into its I/O queue.

When the underlying device returns to its working (D0) state, the framework will redeliver the request to the driver. 

</li>
<li>
Setting <i>Requeue</i> to <b>FALSE</b> causes ownership of the request to remain with the driver. The driver must stop doing any I/O processing that requires hardware access. 

When the underlying device returns to its working (D0) state, the framework will call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackioresume-onioresume">IQueueCallbackIoResume::OnIoResume</a> callback function, so that the driver can continue processing the request.

</li>
</ul>
If the driver had previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a>, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">IWDFIoRequest::UnmarkCancelable</a> before calling <b>StopAcknowledge</b> with <i>Requeue</i> set to <b>TRUE</b>.

Before calling <b>StopAcknowledge</b>, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackiostop-oniostop">IQueueCallbackIoStop::OnIoStop</a> callback function must stop all processing of the I/O request that requires accessing the underlying device, because the device is about to enter a low-power state.


#### Examples

The following code example is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackiostop-oniostop">IQueueCallbackIoStop::OnIoStop</a> callback function that checks to see if a received request is cancelable and, if it is, calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">IWDFIoRequest::UnmarkCancelable</a>. If <b>IWDFIoRequest::UnmarkCancelable</b> returns HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED), the example just returns because the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a> callback function will handle the request. Otherwise, the example calls <b>StopAcknowledge</b> and specifies <b>FALSE</b> so that the framework will eventually call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackioresume-onioresume">IQueueCallbackIoResume::OnIoResume</a> callback function. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void
CMyReadWriteQueue::OnIoStop(
    __in IWDFIoQueue*  pWdfQueue,
    __in IWDFIoRequest*  pWdfRequest,
    __in ULONG  ActionFlags
    )
{ HRESULT status;

    if (ActionFlags & WdfRequestStopRequestCancelable) {
        status = pWdfRequest->UnmarkCancelable();
        if (status == HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED)) {
        return;
        }
    }
    //
    // Declare an IWDFIoRequest2 interface pointer and obtain the
    // IWDFIoRequest2 interface from the IWDFIoRequest interface.
    //
    CComQIPtr<IWDFIoRequest2> r2 = pWdfRequest;

    r2->StopAcknowledge(FALSE);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackioresume-onioresume">IQueueCallbackIoResume::OnIoResume</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iqueuecallbackiostop-oniostop">IQueueCallbackIoStop::OnIoStop</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>
 

 

