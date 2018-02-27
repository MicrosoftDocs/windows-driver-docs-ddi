---
UID: NF:wudfddi.IWDFIoRequest2.GetStatus
title: IWDFIoRequest2::GetStatus method
author: windows-driver-content
description: The GetStatus method returns the status of an I/O request.
old-location: wdf\iwdfiorequest2_getstatus.htm
old-project: wdf
ms.assetid: 20b10edb-3294-4cc7-91bc-07df565a9cf2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: GetStatus method, GetStatus method, IWDFIoRequest2 interface, GetStatus,IWDFIoRequest2.GetStatus, IWDFIoRequest2, IWDFIoRequest2 interface, GetStatus method, IWDFIoRequest2::GetStatus, UMDFRequestObjectRef_c2efd103-5295-494f-8938-95cf0d76fc3e.xml, umdf.iwdfiorequest2_getstatus, wdf.iwdfiorequest2_getstatus, wudfddi/IWDFIoRequest2::GetStatus
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoRequest2.GetStatus
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest2::GetStatus method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetStatus</b> method returns the status of an I/O request.


## -syntax


````
HRESULT GetStatus();
````


## -parameters






## -returns



<b>GetStatus</b> returns an HRESULT-typed status value, This value indicates the current status of the I/O request that the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a> interface represents. 




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
For more information about request completion, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example sends an I/O request to an I/O target. If the call to <a href="https://msdn.microsoft.com/f916b414-9cd9-4745-a021-07c810d0d68b">Send</a> succeeds, the example obtains the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a> interface, calls <b>GetStatus</b> to obtain the request's status value, and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559074">IWDFIoRequest::CompleteWithInformation</a> to complete the I/O request.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559074">IWDFIoRequest::CompleteWithInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559084">IWDFIoRequest::GetCompletionParams</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::GetStatus method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

