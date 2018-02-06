---
UID: NF:wdfrequest.WdfRequestFormatRequestUsingCurrentType
title: WdfRequestFormatRequestUsingCurrentType function
author: windows-driver-content
description: The WdfRequestFormatRequestUsingCurrentType method formats a specified I/O request so that the driver can forward it, unmodified, to the driver's local I/O target.
old-location: wdf\wdfrequestformatrequestusingcurrenttype.htm
old-project: wdf
ms.assetid: 51af6f9e-1e38-4af2-9db8-cfad41e2f435
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfrequestformatrequestusingcurrenttype, kmdf.wdfrequestformatrequestusingcurrenttype, DFRequestObjectRef_c84fc560-9492-448a-9886-754c2857eba5.xml, PFN_WDFREQUESTFORMATREQUESTUSINGCURRENTTYPE, wdfrequest/WdfRequestFormatRequestUsingCurrentType, WdfRequestFormatRequestUsingCurrentType method, WdfRequestFormatRequestUsingCurrentType
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


## -syntax


````
VOID WdfRequestFormatRequestUsingCurrentType(
  _In_ WDFREQUEST Request
);
````


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
Call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> to send the request to the I/O target.

</li>
</ol>For more information about <b>WdfRequestFormatRequestUsingCurrentType</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestwdmformatusingstacklocation.md">WdfRequestWdmFormatUsingStackLocation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestFormatRequestUsingCurrentType method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

