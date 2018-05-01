---
UID: NF:wdfrequest.WdfRequestGetCompletionParams
title: WdfRequestGetCompletionParams function
author: windows-driver-content
description: The WdfRequestGetCompletionParams method retrieves the I/O completion parameters that are associated with a specified framework request object.
old-location: wdf\wdfrequestgetcompletionparams.htm
old-project: wdf
ms.assetid: 167bb0f3-a484-443b-8bc4-bb2bbcecc19a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_032fe29a-4000-4d97-92fb-50462d2c1bea.xml, WdfRequestGetCompletionParams, WdfRequestGetCompletionParams method, kmdf.wdfrequestgetcompletionparams, wdf.wdfrequestgetcompletionparams, wdfrequest/WdfRequestGetCompletionParams
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRequestGetCompletionParams
product: Windows
targetos: Windows
req.typenames: 
---

# WdfRequestGetCompletionParams function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestGetCompletionParams</b> method retrieves the I/O completion parameters that are associated with a specified framework request object.


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param Params [out]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a> structure.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After a driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to synchronously or asynchronously send an I/O request to an I/O target, and after the I/O target has <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completed</a> the I/O request, the driver can call <b>WdfRequestGetCompletionParams</b> to obtain the I/O request's completion parameters.

The completion parameters structure contains valid information only if the driver has formatted the request by calling one of the <b>WdfIoTargetFormat</b><i>Xxx</i> methods. For example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548612">WdfIoTargetFormatRequestForRead</a>.

Note that if your driver calls one of the methods that sends I/O requests to I/O targets only synchronously (such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff548669">WdfIoTargetSendReadSynchronously</a>), the driver must <i>not</i> call <b>WdfRequestGetCompletionParams</b>.

The <b>WdfRequestGetCompletionParams</b> method copies the I/O request's completion parameters into the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a> structure.

If a driver sends an I/O request asynchronously, it typically calls this method from within a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function.

For more information about <b>WdfRequestGetCompletionParams</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a> structure and then calls <b>WdfRequestGetCompletionParams</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_REQUEST_COMPLETION_PARAMS completionParams;

WDF_REQUEST_COMPLETION_PARAMS_INIT(&amp;completionParams);
WdfRequestGetCompletionParams(
                              request,
                              &amp;completionParams
                              );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552456">WDF_REQUEST_COMPLETION_PARAMS_INIT</a>
 

 

