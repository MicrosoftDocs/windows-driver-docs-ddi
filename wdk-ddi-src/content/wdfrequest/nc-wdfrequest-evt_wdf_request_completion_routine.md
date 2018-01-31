---
UID: NC:wdfrequest.EVT_WDF_REQUEST_COMPLETION_ROUTINE
title: EVT_WDF_REQUEST_COMPLETION_ROUTINE
author: windows-driver-content
description: A driver's CompletionRoutine event callback function executes when another driver completes a specified I/O request.
old-location: wdf\completionroutine.htm
old-project: wdf
ms.assetid: 7d3eb4d6-9fc7-4924-9b95-f5824713049b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.completionroutine, CompletionRoutine callback function, CompletionRoutine, EVT_WDF_REQUEST_COMPLETION_ROUTINE, EVT_WDF_REQUEST_COMPLETION_ROUTINE, wdfrequest/CompletionRoutine, DFRequestObjectRef_5eed5273-6939-4a56-846a-ee80c92c005a.xml, kmdf.completionroutine
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
-	CompletionRoutine
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# EVT_WDF_REQUEST_COMPLETION_ROUTINE callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>CompletionRoutine</i> event callback function executes when another driver completes a specified I/O request.


## -prototype


````
EVT_WDF_REQUEST_COMPLETION_ROUTINE CompletionRoutine;

void CompletionRoutine(
  _In_ WDFREQUEST                     Request,
  _In_ WDFIOTARGET                    Target,
  _In_ PWDF_REQUEST_COMPLETION_PARAMS Params,
  _In_ WDFCONTEXT                     Context
)
{ ... }
````


## -parameters




#### - Request [in]

A handle to a framework request object that represents the completed I/O request.


#### - Target [in]

A handle to an I/O target object that represents the I/O target that completed the request.


#### - Params [in]

A pointer to a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a> structure that contains information about the completed request.


#### - Context [in]

Driver-supplied context information, which the driver specified in a previous call to <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetcompletionroutine.md">WdfRequestSetCompletionRoutine</a>.


## -returns


None
<h2><a id="ddk_completionroutine_df"></a><a id="DDK_COMPLETIONROUTINE_DF"></a></h2>


## -remarks


To register a <i>CompletionRoutine</i> callback function for an I/O request, a driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetcompletionroutine.md">WdfRequestSetCompletionRoutine</a>. For more information about this callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.

Note that the completion parameters structure contains valid information only if the driver has formatted the request by calling one of the <b>WdfIoTargetFormat</b><i>Xxx</i> methods. For an example, see <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforread.md">WdfIoTargetFormatRequestForRead</a>.

A KMDF driver's <i>CompletionRoutine</i> can run at IRQL &lt;= DISPATCH_LEVEL regardless of the  <b>ExecutionLevel</b> specified in the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure for the I/O request object.  



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetcompletionroutine.md">WdfRequestSetCompletionRoutine</a>

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_REQUEST_COMPLETION_ROUTINE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

