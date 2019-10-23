---
UID: NC:wdfrequest.EVT_WDF_REQUEST_COMPLETION_ROUTINE
title: EVT_WDF_REQUEST_COMPLETION_ROUTINE (wdfrequest.h)
description: A driver's CompletionRoutine event callback function executes when another driver completes a specified I/O request.
old-location: wdf\completionroutine.htm
tech.root: wdf
ms.assetid: 7d3eb4d6-9fc7-4924-9b95-f5824713049b
ms.date: 02/26/2018
ms.keywords: CompletionRoutine, CompletionRoutine callback function, DFRequestObjectRef_5eed5273-6939-4a56-846a-ee80c92c005a.xml, EVT_WDF_REQUEST_COMPLETION_ROUTINE, EVT_WDF_REQUEST_COMPLETION_ROUTINE callback, kmdf.completionroutine, wdf.completionroutine, wdfrequest/CompletionRoutine
ms.topic: callback
f1_keywords:
 - "wdfrequest/CompletionRoutine"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfrequest.h
api_name:
- CompletionRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_REQUEST_COMPLETION_ROUTINE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>CompletionRoutine</i> event callback function executes when another driver completes a specified I/O request.


## -parameters




### -param Request [in]

A handle to a framework request object that represents the completed I/O request.


### -param Target [in]

A handle to an I/O target object that represents the I/O target that completed the request.


### -param Params [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a> structure that contains information about the completed request.


### -param Context [in]

Driver-supplied context information, which the driver specified in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetcompletionroutine">WdfRequestSetCompletionRoutine</a>.


## -returns



None

<h2><a id="ddk_completionroutine_df"></a><a id="DDK_COMPLETIONROUTINE_DF"></a></h2>



## -remarks



To register a <i>CompletionRoutine</i> callback function for an I/O request, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetcompletionroutine">WdfRequestSetCompletionRoutine</a>. For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.

Note that the completion parameters structure contains valid information only if the driver has formatted the request by calling one of the <b>WdfIoTargetFormat</b><i>Xxx</i> methods. For an example, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetformatrequestforread">WdfIoTargetFormatRequestForRead</a>.

A KMDF driver's <i>CompletionRoutine</i> can run at IRQL <= DISPATCH_LEVEL regardless of the  <b>ExecutionLevel</b> specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure for the I/O request object.  


#### Examples

The function type is declared in <i>Wdfrequest.h</i>, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
  (EVT_WDF_REQUEST_COMPLETION_ROUTINE)(
    IN WDFREQUEST  Request,
    IN WDFIOTARGET  Target,
    IN PWDF_REQUEST_COMPLETION_PARAMS  Params,
    IN WDFCONTEXT  Context
    );
</pre>
</td>
</tr>
</table></span></div>
To define a <i>CompletionRoutine</i> callback function that is named <b>MyCompletionRoutine</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_REQUEST_COMPLETION_ROUTINE  MyCompletionRoutine;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
 MyCompletionRoutine (
    IN WDFREQUEST  Request,
    IN WDFIOTARGET  Target,
    IN PWDF_REQUEST_COMPLETION_PARAMS  Params,
    IN WDFCONTEXT  Context
    )
  {...}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetcompletionroutine">WdfRequestSetCompletionRoutine</a>
 

 

