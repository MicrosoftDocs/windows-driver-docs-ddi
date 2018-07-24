---
UID: NF:wdfrequest.WdfRequestGetInformation
title: WdfRequestGetInformation function
author: windows-driver-content
description: The WdfRequestGetInformation method returns completion status information for a specified I/O request.
old-location: wdf\wdfrequestgetinformation.htm
tech.root: wdf
ms.assetid: fd5f29f7-e9c6-48c4-8704-5db37b8c6337
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_ea947de9-aea4-4e66-8686-f4ca5a1385c4.xml, WdfRequestGetInformation, WdfRequestGetInformation method, kmdf.wdfrequestgetinformation, wdf.wdfrequestgetinformation, wdfrequest/WdfRequestGetInformation
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
-	WdfRequestGetInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestGetInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestGetInformation</b> method returns completion status information for a specified I/O request.


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestGetInformation</b> returns the information that a lower-level driver set by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a> to set completion status information for an I/O request. Your driver can call <b>WdfRequestGetInformation</b> after a lower-level driver completes a request, to obtain completion status information that the lower-level driver set. 

If your driver calls <b>WdfRequestGetInformation</b> after it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request, <b>WdfRequestGetInformation</b> returns <b>NULL</b>.

For more information about <b>WdfRequestGetInformation</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example sends an I/O request to an I/O target and then obtains status information that the I/O target provided.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ULONG_PTR  informationRetrieved = NULL;

status = WdfIoTargetSendWriteSynchronously(
                                           ioTarget,
                                           request,
                                           &amp;outputMemoryDescriptor,
                                           NULL,
                                           NULL,
                                           &amp;bytesWritten
                                           );
if (NT_SUCCESS(status)) {
    informationRetrieved = WdfRequestGetInformation(request);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a>
 

 

