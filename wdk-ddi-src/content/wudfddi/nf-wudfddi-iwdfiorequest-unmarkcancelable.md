---
UID: NF:wudfddi.IWDFIoRequest.UnmarkCancelable
title: IWDFIoRequest::UnmarkCancelable (wudfddi.h)
description: The UnmarkCancelable method disables the canceling of an I/O request.
old-location: wdf\iwdfiorequest_unmarkcancelable.htm
tech.root: wdf
ms.assetid: 5a3fa72c-241e-4270-92eb-70f135d79871
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest interface,UnmarkCancelable method, IWDFIoRequest.UnmarkCancelable, IWDFIoRequest::UnmarkCancelable, UMDFRequestObjectRef_365794c9-1bce-43ef-8ce5-83affed9b18e.xml, UnmarkCancelable, UnmarkCancelable method, UnmarkCancelable method,IWDFIoRequest interface, umdf.iwdfiorequest_unmarkcancelable, wdf.iwdfiorequest_unmarkcancelable, wudfddi/IWDFIoRequest::UnmarkCancelable
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFIoRequest.UnmarkCancelable"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
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
- IWDFIoRequest.UnmarkCancelable
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::UnmarkCancelable


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>UnmarkCancelable</b> method disables the canceling of an I/O request.


## -parameters






## -returns



<b>UnmarkCancelable</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">UnmarkCancelable</a> disabled use of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a> method that was previously registered through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a> method.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_OPERATION_ABORTED)</b></dt>
</dl>
</td>
<td width="60%">
The request is currently being canceled.

</td>
</tr>
</table>
 




## -remarks



A driver can call <b>IWDFIoRequest::UnmarkCancelable</b> to disable cancellation of an I/O request, if the driver previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a> to enable cancellation of the request.

If the driver previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">MarkCancelable</a>, the driver must call <b>UnmarkCancelable</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a> outside of a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a> callback method.

However, the driver must not call <b>UnmarkCancelable</b> after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">OnCancel</a> calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensionrequest-complete">Complete</a>.

If <b>UnmarkCancelable</b> returns HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED), and then <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">OnCancel</a> completes the request, the driver must not subsequently use the request object.

If <b>UnmarkCancelable</b> returns HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED), the driver must not complete the request before the framework calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">OnCancel</a>.  Otherwise, the framework might call the driver's <b>OnCancel</b> with an invalid request.


#### Examples

The following code example demonstrates how a driver might call <b>IWDFIoRequest::UnmarkCancelable</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a>, outside of a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a> method.

The example also shows how you can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">OnCancel</a> to expedite the completion of a request. In this case, the <b>OnCancel</b> callback does not always complete/cancel the specified request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>//
// The driver calls CompletePendingRequest when it is ready to complete the request with error/success.
// You must previously initialize m_CompleteCancelledRequest to zero.
//
VOID
CompletePendingRequest( 
    HRESULT hr,
    DWORD   information
    )
{
    LONG shouldComplete = 1;

    if (m_PendingRequest) {
        HRESULT hrUnmark = m_PendingRequest->UnmarkCancelable();
        if (HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED) == hrUnmark) { 
            //
            // We are racing with OnCancel.  We cannot complete m_PendingRequest until after
            // both IWDFIoRequest::Complete and OnCancel have finished with it. To
            // guarantee this, the last to run (either OnCancel or CompletePendingRequest) will
            // be the one to complete the request. 
            //
            shouldComplete = InterlockedExchange(&m_CompleteCancelledRequest, 1);
        }

        // 
        // If we were first to set m_CompleteCancelledRequest to 1, then drop out here
        // and rely on OnCancel to complete the request.
        // 

        if (1 == shouldComplete) { 
            IWDFIoRequest *FxRequest = (IWDFIoRequest*)InterlockedExchangePointer((PVOID *)&m_PendingRequest, NULL);
            InterlockedExchange(&m_CompleteCancelledRequest, 0);
            FxRequest->SetInformation(information);
            FxRequest->Complete(hr);
        }
   }
}

//
// The framework calls OnCancel when an application cancels a pending I/O request. 
//
VOID
STDMETHODCALLTYPE
OnCancel(
    _In_ IWDFIoRequest *pWdfRequest
    )
{
    if (m_PendingRequest != pWdfRequest) {
        TraceEvents(TRACE_LEVEL_ERROR, 
                    YOURDEVICE_TRACE_DEVICE, 
                    "%!FUNC! Cancelled request does not match pending request.");
    }

    // 
    // Add your code to speed up the completion of the request.  Maybe you need to reset the hardware or 
    // do some other domain-specific task.
    //

    //
    // Since we only complete the request if we were the last to run (see comment in
    // CompletePendingRequest), if we are *not* the last to run we rely on CompletePendingRequest 
    // to complete this request.
    //

    LONG shouldComplete = InterlockedExchange(&m_CompleteCancelledRequest, 1);
    if (1 == shouldComplete) { 
        //
        // Enter this block only if we are the last to run.
        // Otherwise, rely on CompletePendingRequest to complete this request.
        //
        (void*) InterlockedExchangePointer((PVOID *)&m_PendingRequest, NULL);
        InterlockedExchange(&m_CompleteCancelledRequest, 0);
        pWdfRequest->Complete(HRESULT_FROM_WIN32(ERROR_CANCELLED));
     } 
 
}

</pre>
</td>
</tr>
</table></span></div>
In the next code example, the driver stores I/O requests in a driver-implemented queue object called <b>MyQueue</b>.  The driver’s <b>MyQueue</b> interface implements some basic methods to manipulate the queue, such as <b>IsEmpty</b>, <b>RemoveHead</b>, <b>Cleanup</b>, <b>GetFirstNodePosition</b>, <b>GetAt</b>, and <b>RemoveAt</b>.

The driver also defines a <b>CommandInformation</b> structure that holds a single I/O request from <b>MyQueue</b>.

  The <b>MyQueue::DeQueue</b> method removes an I/O request from the queue, calls <b>UnmarkCancelable</b> to disable canceling of the request, and then returns the request for processing.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
void MyQueue::DeQueue(__out CommandInformation* CommandInfo)
{
    CComCritSecLock<CComAutoCriticalSection> scopeLock(m_CriticalSection);

    if (NULL != CommandInfo)
    {
        for (;;) 
        {
            if (TRUE == IsEmpty()) 
            {
                ZeroMemory(CommandInfo, sizeof(CommandInformation));
                break;
            }
            //
            // If queue is not empty, retrieve the first element from the list.
            //
            *CommandInfo = RemoveHead(); 
            if (HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED) != (CommandInfo->Request)->UnmarkCancelable())
            {
                //
                // UnmarkCancelable was successful.
                // Ownership of this request has been transferred back to this driver.
                //
                break;
            }
            else
            {
                //
                // If UMDF returns HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED) for UnmarkCancelable,
                // that means UMDF is planning on cancelling the request. However, since this call
                // popped the request off our internal queue, let’s cleanup the generic command object
                // and let OnCancel complete the request.               
                //                
                CommandInfo->Cleanup();
            }
        }    
    }
}

//
// The framework calls OnCancel when an application cancels a dispatched I/O request.
//
void MyQueue::OnCancel(__in IWDFIoRequest* Request)
{
    {
        CComCritSecLock<CComAutoCriticalSection> scopeLock(m_CriticalSection);

        POSITION pos = GetFirstNodePosition();

        while (NULL != pos)
        {
            //
            // Find the request and remove it from our driver-implemented queue.
            //
            CommandInformation commandInfo = GetAt(pos);
            if (Request == commandInfo.Request)
            {
                RemoveAt(pos);
                commandInfo.Cleanup();
                break;
            }

            GetNext(pos);
        }
    }

    //
    // Cancel/Complete the request.
    //
    // The request might not be in the queue when the framework calls OnCancel. 
    // This occurs if DeQueue receives HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED)
    // when it calls UnmarkCancelable for the request. In this case, as soon as
    // DeQueue releases the scopeLock, the framework calls OnCancel to cancel the request.
    //
    Request->Complete(HRESULT_FROM_WIN32(ERROR_CANCELLED));
}


</pre>
</td>
</tr>
</table></span></div>
Also see the code example on <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>. While written for a KMDF driver, this example demonstrates how you can use the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">automatic synchronization</a> to manage synchronization between the cancel callback and another thread that calls the <i>Unmark</i> routine.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a>
 

 

