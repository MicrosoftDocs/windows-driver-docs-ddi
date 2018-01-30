---
UID: NF:wudfddi.IWDFIoRequest.UnmarkCancelable
title: IWDFIoRequest::UnmarkCancelable method
author: windows-driver-content
description: The UnmarkCancelable method disables the canceling of an I/O request.
old-location: wdf\iwdfiorequest_unmarkcancelable.htm
old-project: wdf
ms.assetid: 5a3fa72c-241e-4270-92eb-70f135d79871
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFIoRequest interface, UnmarkCancelable method, wudfddi/IWDFIoRequest::UnmarkCancelable, umdf.iwdfiorequest_unmarkcancelable, UMDFRequestObjectRef_365794c9-1bce-43ef-8ce5-83affed9b18e.xml, wdf.iwdfiorequest_unmarkcancelable, IWDFIoRequest, UnmarkCancelable, UnmarkCancelable method, IWDFIoRequest interface, UnmarkCancelable method, IWDFIoRequest::UnmarkCancelable
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IWDFIoRequest.UnmarkCancelable
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFIoRequest::UnmarkCancelable method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>UnmarkCancelable</b> method disables the canceling of an I/O request.


## -syntax


````
HRESULT  UnmarkCancelable();
````


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

<a href="https://msdn.microsoft.com/5a3fa72c-241e-4270-92eb-70f135d79871">UnmarkCancelable</a> disabled use of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556903">IRequestCallbackCancel::OnCancel</a> method that was previously registered through a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a> method.

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


A driver can call <b>IWDFIoRequest::UnmarkCancelable</b> to disable cancellation of an I/O request, if the driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a> to enable cancellation of the request.

If the driver previously called <a href="https://msdn.microsoft.com/73e323a4-d40e-4414-92b7-310bfb0f6457">MarkCancelable</a>, the driver must call <b>UnmarkCancelable</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a> outside of a call to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff556903">IRequestCallbackCancel::OnCancel</a> callback method.

However, the driver must not call <b>UnmarkCancelable</b> after <a href="https://msdn.microsoft.com/67c85eaa-bb47-4384-8e37-fdbbc879b352">OnCancel</a> calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh406719">Complete</a>.

If <b>UnmarkCancelable</b> returns HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED), and then <a href="https://msdn.microsoft.com/67c85eaa-bb47-4384-8e37-fdbbc879b352">OnCancel</a> completes the request, the driver must not subsequently use the request object.

If <b>UnmarkCancelable</b> returns HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED), the driver must not complete the request before the framework calls <a href="https://msdn.microsoft.com/67c85eaa-bb47-4384-8e37-fdbbc879b352">OnCancel</a>.  Otherwise, the framework might call the driver's <b>OnCancel</b> with an invalid request.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556903">IRequestCallbackCancel::OnCancel</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::UnmarkCancelable method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

