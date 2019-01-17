---
UID: NF:wudfddi.IWDFIoRequest2.GetStatus
title: IWDFIoRequest2::GetStatus
description: The GetStatus method returns the status of an I/O request.
old-location: wdf\iwdfiorequest2_getstatus.htm
tech.root: wdf
ms.assetid: 20b10edb-3294-4cc7-91bc-07df565a9cf2
ms.date: 02/26/2018
ms.keywords: GetStatus, GetStatus method, GetStatus method,IWDFIoRequest2 interface, IWDFIoRequest2 interface,GetStatus method, IWDFIoRequest2.GetStatus, IWDFIoRequest2::GetStatus, UMDFRequestObjectRef_c2efd103-5295-494f-8938-95cf0d76fc3e.xml, umdf.iwdfiorequest2_getstatus, wdf.iwdfiorequest2_getstatus, wudfddi/IWDFIoRequest2::GetStatus
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest2.GetStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest2::GetStatus


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetStatus</b> method returns the status of an I/O request.


## -parameters






## -returns



<b>GetStatus</b> returns an HRESULT-typed status value, This value indicates the current status of the I/O request that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a> interface represents. 




## -remarks



A driver can call <b>GetStatus</b> after it has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> to send an I/O request to an I/O target. 

<ul>
<li>
If a driver's call to <a href="https://msdn.microsoft.com/f916b414-9cd9-4745-a021-07c810d0d68b">Send</a> succeeds, <b>GetStatus</b> returns the status value that is set by the driver that completes the specified request.

If the driver specifies WDF_REQUEST_SEND_OPTION_SYNCHRONOUS for a request when it calls <a href="https://msdn.microsoft.com/f916b414-9cd9-4745-a021-07c810d0d68b">Send</a>, the driver can call <b>GetStatus</b> (or <a href="https://msdn.microsoft.com/library/windows/hardware/ff559084">IWDFIoRequest::GetCompletionParams</a>) immediately after calling <b>Send</b>.

If the driver does not specify WDF_REQUEST_SEND_OPTION_SYNCHRONOUS when it calls <a href="https://msdn.microsoft.com/f916b414-9cd9-4745-a021-07c810d0d68b">Send</a>, the driver typically calls <b>GetStatus</b> (or <a href="https://msdn.microsoft.com/library/windows/hardware/ff559084">IWDFIoRequest::GetCompletionParams</a>) from within an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a> callback function.

</li>
<li>
If a driver's call to <a href="https://msdn.microsoft.com/f916b414-9cd9-4745-a021-07c810d0d68b">Send</a> fails, <b>Send</b> returns a status value that the framework has set to describe the failure. The driver can call <b>GetStatus</b> (but not<a href="https://msdn.microsoft.com/library/windows/hardware/ff559084">IWDFIoRequest::GetCompletionParams</a>) to obtain the current status of the request, but in this case <b>GetStatus</b> returns the same failure code that <b>Send</b> returned.

</li>
</ul>
For more information about request completion, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example sends an I/O request to an I/O target. If the call to <a href="https://msdn.microsoft.com/f916b414-9cd9-4745-a021-07c810d0d68b">Send</a> succeeds, the example obtains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a> interface, calls <b>GetStatus</b> to obtain the request's status value, and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559074">IWDFIoRequest::CompleteWithInformation</a> to complete the I/O request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT hrSend = S_OK;
...
hrSend = fxRequest-&gt;Send(m_pIoTarget,
                         WDF_REQUEST_SEND_OPTION_SYNCHRONOUS,
                         0);
if (SUCCEEDED(hrSend))
{
    //
    // If send succeeded, complete the request and specify 
    // the current status value.
    //
    CComQIPtr&lt;IWDFIoRequest2&gt; fxRequest2 = fxRequest;
    hrSend = fxRequest2-&gt;GetStatus();
    fxRequest-&gt;CompleteWithInformation(hrSend, 0);
}
...</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559074">IWDFIoRequest::CompleteWithInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559084">IWDFIoRequest::GetCompletionParams</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>
 

 

