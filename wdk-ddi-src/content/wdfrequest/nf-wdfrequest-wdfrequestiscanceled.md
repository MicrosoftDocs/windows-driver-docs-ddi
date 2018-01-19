---
UID: NF:wdfrequest.WdfRequestIsCanceled
title: WdfRequestIsCanceled function
author: windows-driver-content
description: The WdfRequestIsCanceled method determines whether the I/O manager has attempted to cancel a specified I/O request.
old-location: wdf\wdfrequestiscanceled.htm
old-project: wdf
ms.assetid: 73ec4bf1-ba48-4b51-8824-61ce42f9708d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestIsCanceled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRequestIsCanceled
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, ReqIsCancOnCancReq
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestIsCanceled function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestIsCanceled</b> method determines whether the I/O manager has attempted to cancel a specified I/O request.



## -syntax

````
BOOLEAN WdfRequestIsCanceled(
  _In_ WDFREQUEST Request
);
````


## -parameters

### -param Request [in]

A handle to a framework request object.


## -returns
<b>WdfRequestIsCanceled</b> returns <b>TRUE</b> if the I/O manager has attempted to cancel the specified I/O request. This method may return <b>TRUE</b> even if the calling driver does not own the request.  If the driver does not own the request, it should not call <b>WdfRequestIsCanceled</b>. See additional information in Remarks.

<b>WdfRequestIsCanceled</b> returns <b>FALSE</b> for one of the following reasons: 


<ul>
<li>The I/O manager has not attempted to cancel the request.</li>
<li>The calling driver does not own the request. 
</li>
<li>The calling driver has called the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> method. 
</li>
</ul>


A bug check occurs if the driver supplies an invalid object handle.


## -remarks
If your driver has not called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> to register an <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function, but if you want your driver to determine if the I/O manager has attempted to cancel an I/O request, the driver can call <b>WdfRequestIsCanceled</b>.

If the driver has called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>, it must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a> before calling <b>WdfRequestIsCanceled</b>.

A driver can call <b>WdfRequestIsCanceled</b> for a request only if the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">owns</a> the I/O request. 

If <b>WdfRequestIsCanceled</b> returns <b>TRUE</b>, your driver should cancel the request by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> with a <i>Status</i> parameter of STATUS_CANCELLED. If the driver attempts to complete a request that it does not own, the driver can cause the system to crash.

For more information about <b>WdfRequestIsCanceled</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>


The following code example calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> if <b>WdfRequestIsCanceled</b> returns <b>TRUE</b>.


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a>
</dt>
<dt>
<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestIsCanceled method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

