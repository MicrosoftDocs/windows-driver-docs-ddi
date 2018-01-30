---
UID: NF:wdfrequest.WdfRequestWdmFormatUsingStackLocation
title: WdfRequestWdmFormatUsingStackLocation function
author: windows-driver-content
description: The WdfRequestWdmFormatUsingStackLocation method formats an I/O request by copying the contents of a specified WDM I/O stack location structure to the next stack location in the request.
old-location: wdf\wdfrequestwdmformatusingstacklocation.htm
old-project: wdf
ms.assetid: 9ee3d748-f9aa-43d6-b472-7b55d2034fc7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfrequestwdmformatusingstacklocation, WdfRequestWdmFormatUsingStackLocation method, kmdf.wdfrequestwdmformatusingstacklocation, DFRequestObjectRef_a210a31a-e3a5-4bbd-af19-5be5f7651757.xml, wdfrequest/WdfRequestWdmFormatUsingStackLocation, WdfRequestWdmFormatUsingStackLocation, PFN_WDFREQUESTWDMFORMATUSINGSTACKLOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, RequestFormattedValid
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
apiname:
-	WdfRequestWdmFormatUsingStackLocation
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestWdmFormatUsingStackLocation function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestWdmFormatUsingStackLocation</b> method formats an I/O request by copying the contents of a specified WDM <a href="https://msdn.microsoft.com/62c8ee00-c7cb-4aa1-90ab-b8bedbd818ee">I/O stack location</a> structure to the next stack location in the request.


## -syntax


````
VOID WdfRequestWdmFormatUsingStackLocation(
  _In_ WDFREQUEST         Request,
  _In_ PIO_STACK_LOCATION Stack
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param Stack [in]

A pointer to an <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure that contains driver-supplied information. 


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


The <b>WdfRequestWdmFormatUsingStackLocation</b> method copies the information that is supplied by the <i>Stack</i> parameter into the next IRP stack location in the request. 

<b>WdfRequestWdmFormatUsingStackLocation</b> formats the request independent of whether the I/O target object of the request is local or remote.

If you want to set a completion routine for the request, your driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetcompletionroutine.md">WdfRequestSetCompletionRoutine</a> after calling <b>WdfRequestWdmFormatUsingStackLocation</b>.

For more information about <b>WdfRequestWdmFormatUsingStackLocation</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetcompletionroutine.md">WdfRequestSetCompletionRoutine</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestWdmFormatUsingStackLocation method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

