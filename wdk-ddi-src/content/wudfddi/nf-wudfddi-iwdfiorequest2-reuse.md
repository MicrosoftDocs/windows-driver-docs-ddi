---
UID: NF:wudfddi.IWDFIoRequest2.Reuse
title: IWDFIoRequest2::Reuse (wudfddi.h)
description: The Reuse method reinitializes a framework request object so that it can be reused.
old-location: wdf\iwdfiorequest2_reuse.htm
tech.root: wdf
ms.assetid: 21d04633-3b68-4c89-a0b9-81507a1bb6d3
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest2 interface,Reuse method, IWDFIoRequest2.Reuse, IWDFIoRequest2::Reuse, Reuse, Reuse method, Reuse method,IWDFIoRequest2 interface, UMDFRequestObjectRef_887853e7-3603-4793-b1b2-0b72e63b0d5a.xml, umdf.iwdfiorequest2_reuse, wdf.iwdfiorequest2_reuse, wudfddi/IWDFIoRequest2::Reuse
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
- IWDFIoRequest2.Reuse
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest2::Reuse


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Reuse</b> method reinitializes a framework request object so that it can be reused.


## -parameters




### -param hrNewStatus [in]

An HRESULT-typed status value that the framework assigns to the request.


## -returns



None.




## -remarks



If a framework-based driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff557021">IWDFDevice::CreateRequest</a> to create request objects, the driver can reuse those request objects. Drivers can also reuse request objects that they receive from the framework in their I/O queues.

A driver can reuse a request object after the original request has been completed. After a driver has called <b>Reuse</b>, the request's contents must be reinitialized.

If you want the reused request to have an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a> callback function, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559153">IWDFIoRequest::SetCompletionCallback</a> after it calls <b>Reuse</b>.

For more information about <b>Reuse</b>, see <a href="https://msdn.microsoft.com/9e3090a9-62d0-48b3-9f3b-7171dc6d2766">Reusing Framework Request Objects</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a> callback function can obtain the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a> interface and then call <b>Reuse</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void 
STDMETHODCALLTYPE
CMyRemoteDevice::OnCompletion(
    __in IWDFIoRequest*  FxRequest,
    __in IWDFIoTarget*  FxTarget,
    __in IWDFRequestCompletionParams*  Params,
    __in void*  Context
    )
{
...
    CComQIPtr&lt;IWDFIoRequest2&gt; fxRequest2(FxRequest);
    fxRequest2-&gt;Reuse(S_OK);
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559153">IWDFIoRequest::SetCompletionCallback</a>
 

 

