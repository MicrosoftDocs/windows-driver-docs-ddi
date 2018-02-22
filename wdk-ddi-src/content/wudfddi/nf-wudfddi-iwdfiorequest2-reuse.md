---
UID: NF:wudfddi.IWDFIoRequest2.Reuse
title: IWDFIoRequest2::Reuse method
author: windows-driver-content
description: The Reuse method reinitializes a framework request object so that it can be reused.
old-location: wdf\iwdfiorequest2_reuse.htm
old-project: wdf
ms.assetid: 21d04633-3b68-4c89-a0b9-81507a1bb6d3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDFIoRequest2, Reuse method, UMDFRequestObjectRef_887853e7-3603-4793-b1b2-0b72e63b0d5a.xml, wudfddi/IWDFIoRequest2::Reuse, Reuse method, IWDFIoRequest2 interface, umdf.iwdfiorequest2_reuse, IWDFIoRequest2 interface, Reuse method, Reuse, wdf.iwdfiorequest2_reuse, IWDFIoRequest2::Reuse
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
-	IWDFIoRequest2.Reuse
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest2::Reuse method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Reuse</b> method reinitializes a framework request object so that it can be reused.


## -syntax


````
void Reuse(
  [in] HRESULT hrNewStatus
);
````


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

The following code example shows how an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a> callback function can obtain the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a> interface and then call <b>Reuse</b>.

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



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559153">IWDFIoRequest::SetCompletionCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::Reuse method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

