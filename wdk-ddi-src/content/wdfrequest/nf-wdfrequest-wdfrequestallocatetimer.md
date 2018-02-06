---
UID: NF:wdfrequest.WdfRequestAllocateTimer
title: WdfRequestAllocateTimer function
author: windows-driver-content
description: The WdfRequestAllocateTimer method allocates a timer for a specified I/O request.
old-location: wdf\wdfrequestallocatetimer.htm
old-project: wdf
ms.assetid: e77aece7-df27-42d8-8e25-6907a5401ff9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFRequestObjectRef_ae292896-d156-44ae-b0cd-3f807fbc1765.xml, wdfrequest/WdfRequestAllocateTimer, wdf.wdfrequestallocatetimer, kmdf.wdfrequestallocatetimer, PFN_WDFREQUESTALLOCATETIMER, WdfRequestAllocateTimer, WdfRequestAllocateTimer method
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
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRequestAllocateTimer
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestAllocateTimer function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestAllocateTimer</b> method allocates a timer for a specified I/O request.


## -syntax


````
NTSTATUS WdfRequestAllocateTimer(
  _In_ WDFREQUEST Request
);
````


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

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


If your driver specifies a time-out value when calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>, it should call <b>WdfRequestAllocateTimer</b> before calling <b>WdfRequestSend</b>. This ensures that the call to <b>WdfRequestSend</b> will not fail if there are insufficient system resources to allocate a timer.

If a timer is already allocated for the specified request, <b>WdfRequestAllocateTimer</b> returns STATUS_SUCCESS.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>

<a href="..\wdfrequest\nf-wdfrequest-wdf_request_send_options_init.md">WDF_REQUEST_SEND_OPTIONS_INIT</a>

<a href="..\wdfcore\nf-wdfcore-wdf_abs_timeout_in_sec.md">WDF_ABS_TIMEOUT_IN_SEC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestAllocateTimer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

