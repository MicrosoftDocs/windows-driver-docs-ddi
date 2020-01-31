---
UID: NC:wdfrequest.EVT_WDF_REQUEST_CANCEL
title: EVT_WDF_REQUEST_CANCEL (wdfrequest.h)
description: A driver's EvtRequestCancel event callback function handles operations that must be performed when an I/O request is canceled.
old-location: wdf\evtrequestcancel.htm
tech.root: wdf
ms.assetid: db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_fe2e3eee-9f6a-4fd8-afa7-23eb740ccd01.xml, EVT_WDF_REQUEST_CANCEL, EVT_WDF_REQUEST_CANCEL callback, EvtRequestCancel, EvtRequestCancel callback function, kmdf.evtrequestcancel, wdf.evtrequestcancel, wdfrequest/EvtRequestCancel
f1_keywords:
 - "wdfrequest/EvtRequestCancel"
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
- EvtRequestCancel
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_REQUEST_CANCEL callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtRequestCancel</i> event callback function handles operations that must be performed when an I/O request is canceled.


## -parameters




### -param Request [in]

A handle to a framework request object that represents the I/O request that is being canceled.


## -remarks



To register an <i>EvtRequestCancel</i> callback function, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>.

 When the framework calls your driver's <i>EvtRequestCancel</i> callback function, if the driver can cancel the request, it must:

<ol>
<li>
Finish or stop processing the request, along with subrequests that it might have created.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>, specifying a status value of STATUS_CANCELLED.

</li>
</ol>
For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.


#### Examples

To define an <i>EvtRequestCancel</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtRequestCancel</i> callback function that is named <i>MyRequestCancel</i>, use the <b>EVT_WDF_REQUEST_CANCEL</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_REQUEST_CANCEL  MyRequestCancel;</pre>
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
<pre>_Use_decl_annotations_
VOID
 MyRequestCancel (
    WDFREQUEST  Request
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_REQUEST_CANCEL</b> function type is defined in the Wdfrequest.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_REQUEST_CANCEL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>
 

 

