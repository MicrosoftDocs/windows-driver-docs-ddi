---
UID: NF:wdfrequest.WdfRequestIsCanceled
title: WdfRequestIsCanceled function (wdfrequest.h)
description: The WdfRequestIsCanceled method determines whether the I/O manager has attempted to cancel a specified I/O request.
old-location: wdf\wdfrequestiscanceled.htm
tech.root: wdf
ms.assetid: 73ec4bf1-ba48-4b51-8824-61ce42f9708d
ms.date: 02/26/2018
keywords: ["WdfRequestIsCanceled function"]
ms.keywords: DFRequestObjectRef_2306854d-71f7-475f-bd8c-a74e2e6630ca.xml, WdfRequestIsCanceled, WdfRequestIsCanceled method, kmdf.wdfrequestiscanceled, wdf.wdfrequestiscanceled, wdfrequest/WdfRequestIsCanceled
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestIsCanceled
 - wdfrequest/WdfRequestIsCanceled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfRequestIsCanceled
---

# WdfRequestIsCanceled function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestIsCanceled</b> method determines whether the I/O manager has attempted to cancel a specified I/O request.

## -parameters

### -param Request 

[in]
A handle to a framework request object.

## -returns

<b>WdfRequestIsCanceled</b> returns <b>TRUE</b> if the I/O manager has attempted to cancel the specified I/O request. This method may return <b>TRUE</b> even if the calling driver does not own the request.  If the driver does not own the request, it should not call <b>WdfRequestIsCanceled</b>. See additional information in Remarks.

<b>WdfRequestIsCanceled</b> returns <b>FALSE</b> for one of the following reasons: 


<ul>
<li>The I/O manager has not attempted to cancel the request.</li>
<li>The calling driver does not own the request. 
</li>
<li>The calling driver has called the <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a> or <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> method. 
</li>
</ul>


A bug check occurs if the driver supplies an invalid object handle.

## -remarks

If your driver has not called <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a> or <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> to register an <a href="/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function, but if you want your driver to determine if the I/O manager has attempted to cancel an I/O request, the driver can call <b>WdfRequestIsCanceled</b>.

If the driver has called <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a> or <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>, it must call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> before calling <b>WdfRequestIsCanceled</b>.

A driver can call <b>WdfRequestIsCanceled</b> for a request only if the driver <a href="/windows-hardware/drivers/wdf/request-ownership">owns</a> the I/O request. 

If <b>WdfRequestIsCanceled</b> returns <b>TRUE</b>, your driver should cancel the request by calling <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> with a <i>Status</i> parameter of STATUS_CANCELLED. If the driver attempts to complete a request that it does not own, the driver can cause the system to crash.

For more information about <b>WdfRequestIsCanceled</b>, see <a href="/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>



#### Examples

The following code example calls <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> if <b>WdfRequestIsCanceled</b> returns <b>TRUE</b>.

```cpp
if (WdfRequestIsCanceled(request)) {
    WdfRequestComplete(
                       request,
                       STATUS_CANCELLED
                       );
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>