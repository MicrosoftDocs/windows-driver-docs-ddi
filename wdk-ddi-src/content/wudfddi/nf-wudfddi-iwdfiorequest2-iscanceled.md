---
UID: NF:wudfddi.IWDFIoRequest2.IsCanceled
title: IWDFIoRequest2::IsCanceled (wudfddi.h)
description: The IsCanceled method determines whether the I/O manager has attempted to cancel an I/O request.
old-location: wdf\iwdfiorequest2_iscanceled.htm
tech.root: wdf
ms.assetid: 68523fcb-bb0d-492f-b6ae-3dab4f6aa637
ms.date: 02/26/2018
keywords: ["IWDFIoRequest2::IsCanceled"]
ms.keywords: IWDFIoRequest2 interface,IsCanceled method, IWDFIoRequest2.IsCanceled, IWDFIoRequest2::IsCanceled, IsCanceled, IsCanceled method, IsCanceled method,IWDFIoRequest2 interface, UMDFRequestObjectRef_7fdd0046-2e99-4221-9e73-c1bebf6251aa.xml, umdf.iwdfiorequest2_iscanceled, wdf.iwdfiorequest2_iscanceled, wudfddi/IWDFIoRequest2::IsCanceled
f1_keywords:
 - "wudfddi/IWDFIoRequest2.IsCanceled"
 - "IWDFIoRequest2.IsCanceled"
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
- IWDFIoRequest2.IsCanceled
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest2::IsCanceled


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsCanceled</b> method determines whether the I/O manager has attempted to cancel an I/O request.


## -returns



<b>IsCanceled</b> returns <b>TRUE</b> if the I/O manager has attempted to cancel the I/O request. This method returns <b>FALSE</b> for any of the following reasons:


<ul>
<li>The I/O manager has not attempted to cancel the request.</li>
<li>The calling driver does not own the request. 
</li>
<li>The calling driver has called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a> method.</li>
</ul>





## -remarks



If your driver has not called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a> to register an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a> callback function, but if you want your driver to determine if the I/O manager has attempted to cancel an I/O request, the driver can call <b>IsCanceled</b>.

A driver can call <b>IsCanceled</b> for a request only if the driver owns the I/O request. If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a>, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">IWDFIoRequest::UnmarkCancelable</a> before calling <b>IsCanceled</b>.

If <b>IsCanceled</b> returns <b>TRUE</b>, your driver should cancel the request by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a> with the <i>CompletionStatus</i> parameter set to HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED).

For more information about <b>IsCanceled</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.


#### Examples

In the following code example, if <b>IsCanceled</b> returns <b>TRUE</b>, the driver completes the I/O request by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a> with a completion status of HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED).

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>if (fxRequest2->IsCanceled())
{
    fxRequest2->Complete(HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED));
}
...</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">IWDFIoRequest::UnmarkCancelable</a>
 

 

