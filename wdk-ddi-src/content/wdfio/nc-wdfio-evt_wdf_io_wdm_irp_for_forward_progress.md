---
UID: NC:wdfio.EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS
title: EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS (wdfio.h)
description: A driver's EvtIoWdmIrpForForwardProgress callback function examines an I/O request packet (IRP) and determines whether to use a reserved request object to process the I/O request or to fail the I/O request.
old-location: wdf\evtiowdmirpforforwardprogress.htm
tech.root: wdf
ms.assetid: 71974802-954d-4856-a32b-1dcc45c36ba5
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_479581ba-4ffd-4aae-b4f0-c246daf38842.xml, EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS, EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS callback, EvtIoWdmIrpForForwardProgress, EvtIoWdmIrpForForwardProgress callback function, kmdf.evtiowdmirpforforwardprogress, wdf.evtiowdmirpforforwardprogress, wdfio/EvtIoWdmIrpForForwardProgress
ms.topic: callback
f1_keywords:
 - "wdfio/EvtIoWdmIrpForForwardProgress"
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfio.h
api_name:
- EvtIoWdmIrpForForwardProgress
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtIoWdmIrpForForwardProgress</i> callback function examines an I/O request packet (IRP) and determines whether to use a reserved request object to process the I/O request or to fail the I/O request.


## -parameters




### -param Queue [in]

A handle to an I/O queue object.


### -param Irp [in]

A pointer to an IRP structure.


## -returns



The <i>EvtIoWdmIrpForForwardProgress</i> callback function must return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_forward_progress_action">WDF_IO_FORWARD_PROGRESS_ACTION</a>-typed value.




## -remarks



A driver can register an <i>EvtIoWdmIrpForForwardProgress</i> callback function when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>.

If your driver registers an <i>EvtIoWdmIrpForForwardProgress</i> callback function, the framework calls the function if all of the following conditions exist:

<ul>
<li>
The framework has received a I/O request packet (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>) that the I/O manager is sending to the driver.

</li>
<li>
The framework has attempted to create a request object for the IRP, but the attempt failed.

</li>
<li>
The driver has enabled guaranteed forward progress for the I/O queue that should receive the request object, with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_forward_progress_reserved_policy">policy type</a> set to <b>WdfIoForwardProgressReservedPolicyUseExamine</b>.

</li>
</ul>
The framework passes the IRP to the <i>EvtIoWdmIrpForForwardProgress</i> callback function. The callback function must examine the IRP and determine whether the framework should use one of its reserved request objects for the IRP or (if the IRP is not important when the computer's available memory is low) fail the I/O request without delivering it to the driver. The callback function's return value specifies the action that the framework should take.

For more information about the <i>EvtIoWdmIrpForForwardProgress</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">Guaranteeing Forward Progress of I/O Operations</a>.

This callback function can be called at IRQL <= DISPATCH_LEVEL. If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions">critical region</a>.


#### Examples

To define an <i>EvtIoWdmIrpForForwardProgress</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoWdmIrpForForwardProgress</i> callback function that is named <i>MyIoForwardExamineIrpForForwardProgress</i>, use the <b>EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS  MyIoWdmIrpForForwardProgress;</pre>
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
WDF_IO_FORWARD_PROGRESS_ACTION
 MyIoWdmIrpForForwardProgress(
    WDFQUEUE  Queue,
    PIRP  Irp
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS</b> function type is defined in the Wdfinterrupt.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_allocate_request_resources">EvtIoAllocateRequestResources</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request">EvtIoAllocateResourcesForReservedRequest</a>
 

 

