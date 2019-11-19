---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_WORKITEM
title: EVT_WDF_INTERRUPT_WORKITEM (wdfinterrupt.h)
description: A driver's EvtInterruptWorkItem event callback function processes interrupt information that the driver's EvtInterruptIsr callback function has stored.
old-location: wdf\evtinterruptworkitem.htm
tech.root: wdf
ms.assetid: 1A473A08-EA23-4DFE-8B58-EBB4AC977891
ms.date: 02/26/2018
ms.keywords: EVT_WDF_INTERRUPT_WORKITEM, EVT_WDF_INTERRUPT_WORKITEM callback, EvtInterruptWorkItem, EvtInterruptWorkItem callback function, kmdf.evtinterruptworkitem, wdf.evtinterruptworkitem, wdfinterrupt/EvtInterruptWorkItem
ms.topic: callback
f1_keywords:
 - "wdfinterrupt/EvtInterruptWorkItem"
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfinterrupt.h
api_name:
- EvtInterruptWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_INTERRUPT_WORKITEM callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtInterruptWorkItem</i> event callback function processes interrupt information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function has stored.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param AssociatedObject [in]

A handle to the framework device object that the driver passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>.


## -remarks



The <i>EvtInterruptWorkItem</i> callback function runs at IRQL = PASSIVE_LEVEL.

To register an <i>EvtInterruptWorkItem</i> callback function, your driver must place the callback function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>.

Most drivers use a single <i>EvtInterruptWorkItem</i> callback function for each type of interrupt. 


To schedule execution of an <i>EvtInterruptWorkItem</i> callback function, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptqueueworkitemforisr">WdfInterruptQueueWorkItemForIsr</a> from within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function.

If your driver creates multiple framework interrupt objects for each device, you might consider using a separate <i>EvtInterruptWorkItem</i> callback for each interrupt.


Drivers that implement either DIRQL  interrupt handling or passive level interrupt handling can queue an <i>EvtInterruptWorkItem</i> callback.

 A driver cannot queue both an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> and a <i>EvtInterruptWorkItem</i> callback.

If the driver has set the <b>AutomaticSerialization</b> member to TRUE in the interrupt's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure, the framework  synchronizes execution of the interrupt object's <i>EvtInterruptWorkItem</i> callback function with callback functions from other objects that are underneath the interrupt's parent object.  For information about callback synchronization locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-locks">Using Framework Locks</a>.

 In general, if the driver needs to acquire the interrupt object's passive lock from within <i>EvtInterruptWorkItem</i>, the driver should set the <b>AutomaticSerialization</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> to FALSE and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a> from within <i>EvtInterruptWorkItem</i>.

If  <b>AutomaticSerialization</b> is set to TRUE, a driver's <i>EvtInterruptWorkItem</i>  callback function should not call any of the following methods:

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptsynchronize">WdfInterruptSynchronize</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptdisable">WdfInterruptDisable</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptenable">WdfInterruptEnable</a>
For more information about handling interrupts in framework-based drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.


#### Examples

To define an <i>EvtInterruptWorkItem</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtInterruptWorkItem</i> callback function that is named <i>MyInterruptWorkItem</i>, use the <b>EVT_WDF_INTERRUPT_WORKITEM</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_INTERRUPT_WORKITEM MyInterruptWorkItem;</pre>
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
 MyInterruptWorkItem (
    WDFINTERRUPT  Interrupt,
    WDFOBJECT  AssociatedObject
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_INTERRUPT_WORKITEM</b> function type is defined in the Wdfinterrupt.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_INTERRUPT_WORKITEM</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.



