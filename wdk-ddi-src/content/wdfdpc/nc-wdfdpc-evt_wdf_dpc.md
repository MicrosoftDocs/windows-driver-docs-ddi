---
UID: NC:wdfdpc.EVT_WDF_DPC
title: EVT_WDF_DPC (wdfdpc.h)
description: A driver's EvtDpcFunc callback function performs driver-defined operations at IRQL = DISPATCH_LEVEL.
old-location: wdf\evtdpcfunc.htm
tech.root: wdf
ms.assetid: b934a0da-0709-4427-bbf2-8d53f9511cf1
ms.date: 02/26/2018
keywords: ["EVT_WDF_DPC callback function"]
ms.keywords: DFDpcObjectRef_ed441283-63f3-4ad3-84fc-05fb2404f634.xml, EVT_WDF_DPC, EVT_WDF_DPC callback, EvtDpcFunc, EvtDpcFunc callback function, kmdf.evtdpcfunc, wdf.evtdpcfunc, wdfdpc/EvtDpcFunc
f1_keywords:
 - "wdfdpc/EvtDpcFunc"
req.header: wdfdpc.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdpc.h
api_name:
- EvtDpcFunc
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DPC callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDpcFunc</i> callback function performs driver-defined operations at IRQL = DISPATCH_LEVEL.


## -parameters




### -param Dpc [in]

A handle to a framework DPC object.


## -remarks



To register an <i>EvtDpcFunc</i> callback function, your driver must place the function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/ns-wdfdpc-_wdf_dpc_config">WDF_DPC_CONFIG</a> structure and call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpccreate">WdfDpcCreate</a>.

Drivers typically <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">complete I/O requests</a> in their <i>EvtDpcFunc</i> callback functions.

The <i>EvtDpcFunc</i> callback function executes at DISPATCH_LEVEL and must not access <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/making-drivers-pageable">pageable</a> code. If an <i>EvtDpcFunc</i> callback function must perform operations at IRQL = PASSIVE_LEVEL, it can <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-work-items">use framework work items</a>.

Instead of providing <i>EvtDpcFunc</i> callback functions, many drivers provide a single <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function for each type of interrupt that its devices support. If your driver creates multiple <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-queue-objects">framework queue objects</a> for each device, you might consider using a separate DPC object and <i>EvtDpcFunc</i> callback function for each queue.

To schedule execution of an <i>EvtDpcFunc</i> callback function, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpcenqueue">WdfDpcEnqueue</a>. Drivers typically call <b>WdfDpcEnqueue</b> from an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function.

When a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpcenqueue">WdfDpcEnqueue</a>, the system adds the DPC object to the system's DPC queue. If the system is not executing higher-priority tasks, it removes the object from the queue and calls the object's <i>EvtDpcFunc</i> callback function. 

The system does not add the DPC object to the DPC queue if the object is already queued. An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function might be called several times before the system calls the <i>EvtDpcFunc</i> callback function. Therefore, the <i>EvtDpcFunc</i> callback function must be able to process information from several interrupts, and it must process all of the interrupts that have occurred since the last time it was called.

Typically, it is necessary to synchronize the execution of a driver's <i>EvtDpcFunc</i> callback function with the execution of other callback functions. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronizing-interrupt-code">Synchronizing Interrupt Code</a>.

To obtain a handle to a DPC object's parent object, the <i>EvtDpcFunc</i> callback function can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpcgetparentobject">WdfDpcGetParentObject</a>. To obtain a pointer to a DPC object's underlying <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure, the <i>EvtDpcFunc</i> callback function can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpcwdmgetdpc">WdfDpcWdmGetDpc</a>.

For more information about using <i>EvtDpcFunc</i> callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/servicing-an-interrupt">Servicing an Interrupt</a>.


#### Examples

To define an <i>EvtDpcFunc</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDpcFunc</i> callback function that is named <i>MyDpcFunc</i>, use the <b>EVT_WDF_DPC</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DPC  MyDpcFunc;</pre>
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
 MyDpcFunc (
    WDFDPC  Dpc
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DPC</b> function type is defined in the Wdfdpc.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DPC</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/ns-wdfdpc-_wdf_dpc_config">WDF_DPC_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpccreate">WdfDpcCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpcenqueue">WdfDpcEnqueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpcgetparentobject">WdfDpcGetParentObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpcwdmgetdpc">WdfDpcWdmGetDpc</a>
 

 

