---
UID: NF:wdfrequest.WdfRequestFormatRequestUsingCurrentType
title: WdfRequestFormatRequestUsingCurrentType function
author: windows-driver-content
description: The WdfRequestFormatRequestUsingCurrentType method formats a specified I/O request so that the driver can forward it, unmodified, to the driver's local I/O target.
old-location: wdf\wdfrequestformatrequestusingcurrenttype.htm
old-project: wdf
ms.assetid: 51af6f9e-1e38-4af2-9db8-cfad41e2f435
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_c84fc560-9492-448a-9886-754c2857eba5.xml, WdfRequestFormatRequestUsingCurrentType, WdfRequestFormatRequestUsingCurrentType method, kmdf.wdfrequestformatrequestusingcurrenttype, wdf.wdfrequestformatrequestusingcurrenttype, wdfrequest/WdfRequestFormatRequestUsingCurrentType
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
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, RequestFormattedValid
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
-	WdfRequestFormatRequestUsingCurrentType
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestFormatRequestUsingCurrentType function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestFormatRequestUsingCurrentType</b> method formats a specified I/O request so that the driver can <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">forward</a> it, unmodified, to the driver's local I/O target.


## -parameters




### -param Request [in]

A handle to a framework request object that the driver received from one of its I/O queues.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



When your driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/receiving-i-o-requests">receives an I/O request</a>, sometimes you will want the driver to forward the request, unmodified, to its local I/O target. To forward such a request, the driver must:

<ol>
<li>
Call <b>WdfRequestFormatRequestUsingCurrentType</b> to format the request object so that the framework can pass the request to the driver's local I/O target.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send the request to the I/O target.

</li>
</ol>
For more information about <b>WdfRequestFormatRequestUsingCurrentType</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.


#### Examples

The following code example is an <a href="https://msdn.microsoft.com/0b834d01-5603-43e8-9b74-9292610cc06d">EvtIoDefault</a> callback function that forwards every I/O request that it receives, without modification, to the device's local I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyEvtIoDefault(
    WDFQUEUE Queue,
    WDFREQUEST Request
    )
{
    WDF_REQUEST_SEND_OPTIONS options;
    NTSTATUS status;
    WDF_REQUEST_PARAMETERS params;
    BOOLEAN ret;

    WDF_REQUEST_PARAMETERS_INIT(&amp;params);

    WdfRequestGetParameters(
                            Request,
                            &amp;params
                            );

    WdfRequestFormatRequestUsingCurrentType(Request);

    WDF_REQUEST_SEND_OPTIONS_INIT(
                                  &amp;options,
                                  WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET
                                  );

    ret = WdfRequestSend (
                          Request,
                          WdfDeviceGetIoTarget(WdfIoQueueGetDevice(Queue)),
                          &amp;options
                          );
    if (!ret) {
        status = WdfRequestGetStatus(Request);
        WdfRequestComplete(
                           Request,
                           status
                           );
    }
    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550036">WdfRequestWdmFormatUsingStackLocation</a>
 

 

