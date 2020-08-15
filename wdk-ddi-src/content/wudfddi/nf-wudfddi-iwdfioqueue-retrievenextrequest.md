---
UID: NF:wudfddi.IWDFIoQueue.RetrieveNextRequest
title: IWDFIoQueue::RetrieveNextRequest (wudfddi.h)
description: The RetrieveNextRequest method retrieves the next I/O request from an I/O queue.
old-location: wdf\iwdfioqueue_retrievenextrequest.htm
tech.root: wdf
ms.assetid: 2d9dbfc8-7563-4c47-9b34-27cce2b847b2
ms.date: 02/26/2018
keywords: ["IWDFIoQueue::RetrieveNextRequest"]
ms.keywords: IWDFIoQueue interface,RetrieveNextRequest method, IWDFIoQueue.RetrieveNextRequest, IWDFIoQueue::RetrieveNextRequest, RetrieveNextRequest, RetrieveNextRequest method, RetrieveNextRequest method,IWDFIoQueue interface, UMDFQueueObjectRef_d76f57ad-f8d5-4a09-861f-26c6d5e6a709.xml, umdf.iwdfioqueue_retrievenextrequest, wdf.iwdfioqueue_retrievenextrequest, wudfddi/IWDFIoQueue::RetrieveNextRequest
f1_keywords:
 - "wudfddi/IWDFIoQueue.RetrieveNextRequest"
 - "IWDFIoQueue.RetrieveNextRequest"
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
- IWDFIoQueue.RetrieveNextRequest
targetos: Windows
req.typenames: 
---

# IWDFIoQueue::RetrieveNextRequest


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveNextRequest</b> method retrieves the next I/O request from an I/O queue.


## -parameters




### -param ppRequest 
[out]
A pointer to a buffer that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface for the next request object, or receives <b>NULL</b> if the queue is empty or if the next request is not found.


## -returns



<b>RetrieveNextRequest</b> returns one of the following values:

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
The next I/O request was successfully retrieved from the I/O queue.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT (STATUS_WDF_PAUSED)</b></dt>
</dl>
</td>
<td width="60%">
The queue is not dispatching requests. This situation occurs if the device undergoes a power state transition and all of the queues are stopped from dispatching requests or if the driver explicitly called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-stop">IWDFIoQueue::Stop</a> to stop dispatching requests. This situation can also occur if the driver attempts to remove a request from a manual queue that is power managed and that is powered down or if the queue is paused.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_NO_MORE_ITEMS)</b></dt>
</dl>
</td>
<td width="60%">
No requests were in the queue.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT (STATUS_INVALID_DEVICE_STATE)</b></dt>
</dl>
</td>
<td width="60%">
The call was made to retrieve the request from a parallel queue.

</td>
</tr>
</table>
 

<b>RetrieveNextRequest</b> might also return other HRESULT values.




## -remarks



If a driver configures an I/O queue for manual dispatching of I/O requests, the driver can call the <b>RetrieveNextRequest</b> method to obtain the next request from the queue. For more information about manually dispatching I/O requests, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/configuring-dispatch-mode-for-an-i-o-queue">Configuring Dispatch Mode for an I/O Queue</a>.

If a driver configures an I/O queue for sequential dispatching of I/O requests, the driver can still call the <b>RetrieveNextRequest</b> method to obtain the next request from the queue without receiving an error. Although the framework permits the driver to call <b>RetrieveNextRequest</b> to retrieve a request from a sequential queue, the driver should only call <b>RetrieveNextRequest</b> before the driver completes the current request. Otherwise, if the driver attempts to call <b>RetrieveNextRequest</b> after the driver completes the current request, a race condition might occur. This race condition occurs between the framework's automatic dispatching of the next request from the sequential queue and the driver's call to <b>RetrieveNextRequest</b> to retrieve the next request. 


#### Examples

The following code example, which is from the <a href="https://go.microsoft.com/fwlink/p/?linkid=256202">umdf_fx2</a> sample driver, polls the queue for requests for as long as requests can be retrieved. The code first verifies if requests are associated with a specific file object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
CMyDevice::ServiceSwitchChangeQueue(
    __in SWITCH_STATE NewState,
    __in HRESULT CompletionStatus,
    __in_opt IWDFFile *SpecificFile
    )
{
    IWDFIoRequest *fxRequest;
    HRESULT enumHr = S_OK;
    do {
        HRESULT hr;
        //
        // Get the next request.
        //
        if (NULL != SpecificFile) {
        enumHr = m_SwitchChangeQueue->RetrieveNextRequestByFileObject(
                                        SpecificFile,
                                        &fxRequest
                                        );
        }
        else {
            enumHr = m_SwitchChangeQueue->RetrieveNextRequest(&fxRequest);
        }
        //
        // If a request was retrieved, complete it.
        //
        if (S_OK == enumHr) {
            if (S_OK == CompletionStatus) {
                IWDFMemory *fxMemory;
                //
                // Copy the result to the request buffer.
                //
                fxRequest->GetOutputMemory(&fxMemory);
                hr = fxMemory->CopyFromBuffer(0, 
                                              &NewState, 
                                              sizeof(SWITCH_STATE));
                                              fxMemory->Release();
            }
            else {
                 hr = CompletionStatus;
            }
            //
            // Complete the request with the copy or 
            // completion status.
            //
            if (S_OK == hr) {
                fxRequest->CompleteWithInformation(hr, 
                                                   sizeof(SWITCH_STATE));
            }
            else {
                fxRequest->Complete(hr);
            }
            fxRequest->Release();
        }
    }
    while (S_OK == enumHr);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-stop">IWDFIoQueue::Stop</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>
 

 

