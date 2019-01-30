---
UID: NF:wudfddi.IWDFIoRequest.Send
title: IWDFIoRequest::Send (wudfddi.h)
description: The Send method sends a request to the specified I/O target.
old-location: wdf\iwdfiorequest_send.htm
tech.root: wdf
ms.assetid: f916b414-9cd9-4745-a021-07c810d0d68b
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest interface,Send method, IWDFIoRequest.Send, IWDFIoRequest::Send, Send, Send method, Send method,IWDFIoRequest interface, UMDFRequestObjectRef_f3a8e812-392d-478c-8234-8125bec14f1d.xml, umdf.iwdfiorequest_send, wdf.iwdfiorequest_send, wudfddi/IWDFIoRequest::Send
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest.Send
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::Send


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Send</b> method sends a request to the specified I/O target.


## -parameters




### -param pIoTarget [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a> interface for the I/O target object, which typically represents a lower driver in the stack. 


### -param Flags [in]

A valid bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552493">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>-typed flags.


### -param Timeout [in]

The amount of time, in system time units (100-nanosecond intervals), that can elapse before the framework automatically cancels the I/O request.

<ul>
<li>
If the value is negative, the expiration time is relative to the current system time.

</li>
<li>
If the value is positive, the expiration time is specified as an absolute time (which is relative to January 1, 1601).

</li>
<li>
If the value is zero, the framework does not time out the request.

</li>
</ul>
Relative expiration times are not affected by any changes to the system time that might occur within the specified time-out period. Absolute expiration times reflect system time changes.


## -returns



<b>Send</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

Note that the return value represents the status of the <b>Send</b> method's attempt to send the I/O request to the I/O target. The return value does not represent the completion status of the I/O request. Your driver must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560292">IWDFRequestCompletionParams</a> interface to obtain the I/O request's completion status.




## -remarks



If <b>Send</b> returns an error code, the driver should typically complete the request with the error code that <b>Send</b> returned, as the code in the following Example section shows.

If your driver sets the WDF_REQUEST_SEND_OPTION_SYNCHRONOUS flag in the <i>Flags</i> parameter, and if <b>Send</b> successfully sends the I/O request to the I/O target, <b>Send</b> returns after the I/O target completes the I/O request. In this case, <b>Send</b> returns S_OK and the driver can immediately call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559084">IWDFIoRequest::GetCompletionParams</a> to obtain the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560292">IWDFRequestCompletionParams</a> interface. The code example at <b>IWDFIoRequest::GetCompletionParams</b> shows a call to <b>Send</b> with the WDF_REQUEST_SEND_OPTION_SYNCHRONOUS flag set.

If your driver does not set the WDF_REQUEST_SEND_OPTION_SYNCHRONOUS flag, and if <b>Send</b> successfully sends the I/O request to the I/O target, <b>Send</b> returns S_OK while the I/O target is still processing the I/O request asynchronously. In this case, the driver provides an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a> callback function that the framework calls after the I/O target completes the I/O request. Typically, the <b>OnCompletion</b> callback function calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559084">IWDFIoRequest::GetCompletionParams</a>. The code example in the following Example section shows a call to <b>Send</b> without the WDF_REQUEST_SEND_OPTION_SYNCHRONOUS flag.

A driver cannot call <b>Send</b> to send an I/O request to a USB pipe, if the driver has configured a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes-in-umdf-1-x-drivers">continuous reader</a> for the pipe.


#### Examples

The following code example forwards a request to a device's I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    IWDFIoRequest* FxRequest;

    //
    // Set the completion callback.
    // When the lower request is completed, the driver is 
    // notified through the completion callback. 
    //

    IRequestCallbackRequestCompletion *completionCallback = 
        QueryIRequestCallbackRequestCompletion();
 
    FxRequest-&gt;SetCompletionCallback(
                                     completionCallback,
                                     NULL  //pContext
                                     );

    completionCallback-&gt;Release();
 
    //
    // Format the I/O request.  
 
    FxRequest-&gt;FormatUsingCurrentType( );

    //
    // Send down the request.
    //
    HRESULT hrSend = S_OK;
 
    hrSend = FxRequest-&gt;Send(
                             m_FxIoTarget,
                             0, // Asynchronous
                             0  // No time-out
                             );
 
    if (S_OK != hrSend) {
        //
        // If the send failed, the driver must complete the 
        // request with the failure.
        FxRequest-&gt;CompleteWithInformation(hrSend, 0);
    }</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559084">IWDFIoRequest::GetCompletionParams</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561462">WDF_REQUEST_SEND_OPTIONS_FLAGS (UMDF)</a>
 

 

