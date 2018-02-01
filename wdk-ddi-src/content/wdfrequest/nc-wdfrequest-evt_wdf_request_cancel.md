---
UID: NC:wdfrequest.EVT_WDF_REQUEST_CANCEL
title: EVT_WDF_REQUEST_CANCEL
author: windows-driver-content
description: A driver's EvtRequestCancel event callback function handles operations that must be performed when an I/O request is canceled.
old-location: wdf\evtrequestcancel.htm
old-project: wdf
ms.assetid: db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtrequestcancel, EvtRequestCancel callback function, EvtRequestCancel, EVT_WDF_REQUEST_CANCEL, EVT_WDF_REQUEST_CANCEL, wdfrequest/EvtRequestCancel, DFRequestObjectRef_fe2e3eee-9f6a-4fd8-afa7-23eb740ccd01.xml, kmdf.evtrequestcancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfrequest.h
apiname:
-	EvtRequestCancel
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# EVT_WDF_REQUEST_CANCEL callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtRequestCancel</i> event callback function handles operations that must be performed when an I/O request is canceled.


## -prototype


````
EVT_WDF_REQUEST_CANCEL EvtRequestCancel;

VOID EvtRequestCancel(
  _In_ WDFREQUEST Request
)
{ ... }
````


## -parameters




### -param Request [in]

A handle to a framework request object that represents the I/O request that is being canceled.


## -returns


None



## -remarks


To register an <i>EvtRequestCancel</i> callback function, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>.

 When the framework calls your driver's <i>EvtRequestCancel</i> callback function, if the driver can cancel the request, it must:
<ol>
<li>
Finish or stop processing the request, along with subrequests that it might have created.

</li>
<li>
Call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>, specifying a status value of STATUS_CANCELLED.

</li>
</ol>For more information about this callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_REQUEST_CANCEL callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

