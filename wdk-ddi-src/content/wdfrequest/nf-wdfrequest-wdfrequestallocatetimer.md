---
UID: NF:wdfrequest.WdfRequestAllocateTimer
title: WdfRequestAllocateTimer function (wdfrequest.h)
description: The WdfRequestAllocateTimer method allocates a timer for a specified I/O request.
old-location: wdf\wdfrequestallocatetimer.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfRequestAllocateTimer function"]
ms.keywords: DFRequestObjectRef_ae292896-d156-44ae-b0cd-3f807fbc1765.xml, WdfRequestAllocateTimer, WdfRequestAllocateTimer method, kmdf.wdfrequestallocatetimer, wdf.wdfrequestallocatetimer, wdfrequest/WdfRequestAllocateTimer
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
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
 - WdfRequestAllocateTimer
 - wdfrequest/WdfRequestAllocateTimer
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
 - WdfRequestAllocateTimer
---

# WdfRequestAllocateTimer function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestAllocateTimer</b> method allocates a timer for a specified I/O request.

## -parameters

### -param Request [in]


A handle to a framework request object.

## -returns

<b>WdfRequestAllocateTimer</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A timer could not be allocated.

</td>
</tr>
</table>
 

This method also might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

If your driver specifies a time-out value when calling <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>, it should call <b>WdfRequestAllocateTimer</b> before calling <b>WdfRequestSend</b>. This ensures that the call to <b>WdfRequestSend</b> will not fail if there are insufficient system resources to allocate a timer.

If a timer is already allocated for the specified request, <b>WdfRequestAllocateTimer</b> returns STATUS_SUCCESS.


#### Examples

The following code example initializes a <a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure, allocates a timer object for the I/O request, and then calls <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>.

```cpp
NTSTATUS  status;
WDF_REQUEST_SEND_OPTIONS  options;
BOOLEAN  requestSend;

WDF_REQUEST_SEND_OPTIONS_INIT(
                              &options,
                              WDF_REQUEST_SEND_OPTION_TIMEOUT
                              );

WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT(
                                     &options,
                                     WDF_ABS_TIMEOUT_IN_SEC(TIME_OUT_VALUE)
                                     );
status = WdfRequestAllocateTimer(
                                 request
                                 );
if (!NT_SUCCESS(status)){
    return status;
...
    requestSend = WdfRequestSend(
                                 request,
                                 ioTarget,
                                 &options
                                 );
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfcore/nf-wdfcore-wdf_abs_timeout_in_sec">WDF_ABS_TIMEOUT_IN_SEC</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_send_options_init">WDF_REQUEST_SEND_OPTIONS_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>
