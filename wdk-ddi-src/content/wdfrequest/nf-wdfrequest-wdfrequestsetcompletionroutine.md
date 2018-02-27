---
UID: NF:wdfrequest.WdfRequestSetCompletionRoutine
title: WdfRequestSetCompletionRoutine function
author: windows-driver-content
description: The WdfRequestSetCompletionRoutine method registers or deregisters a completion routine for the specified framework request object.
old-location: wdf\wdfrequestsetcompletionroutine.htm
old-project: wdf
ms.assetid: c60f3dd5-2a74-4d7c-8804-35b9dd91dce4
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFRequestObjectRef_4dea9104-1bfd-4add-b991-f02d57f840cb.xml, WdfRequestSetCompletionRoutine, WdfRequestSetCompletionRoutine method, kmdf.wdfrequestsetcompletionroutine, wdf.wdfrequestsetcompletionroutine, wdfrequest/WdfRequestSetCompletionRoutine
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
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, ReqCompletionRoutine
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
-	WdfRequestSetCompletionRoutine
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestSetCompletionRoutine function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestSetCompletionRoutine</b> method registers or deregisters a completion routine for the specified framework request object.


## -syntax


````
VOID WdfRequestSetCompletionRoutine(
  _In_     WDFREQUEST                         Request,
  _In_opt_ PFN_WDF_REQUEST_COMPLETION_ROUTINE CompletionRoutine,
  _In_opt_ WDFCONTEXT                         CompletionContext
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param CompletionRoutine [in, optional]

A pointer to a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function, if the driver is registering a completion routine, or <b>NULL</b> of the driver is deregistering a previously registered completion routine.


### -param CompletionContext [in, optional]

An untyped pointer to driver-defined context information that the framework passes to the <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function. This parameter is optional and can be <b>NULL</b>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



If your driver forwards I/O requests, but if you want your driver to be notified when a lower-level driver completes the request, your driver can provide a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function and call <b>WdfRequestSetCompletionRoutine</b> to register the function. The framework calls the callback function after a lower-level driver completes the I/O request. 

For more information about <b>WdfRequestSetCompletionRoutine</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

For a code example that uses <b>WdfRequestSetCompletionRoutine</b>, see <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestSetCompletionRoutine method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

