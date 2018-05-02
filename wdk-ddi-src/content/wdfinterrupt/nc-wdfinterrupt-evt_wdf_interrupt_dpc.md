---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_DPC
title: EVT_WDF_INTERRUPT_DPC
author: windows-driver-content
description: A driver's EvtInterruptDpc event callback function processes interrupt information that the driver's EvtInterruptIsr callback function has stored.
old-location: wdf\evtinterruptdpc.htm
old-project: wdf
ms.assetid: d2d505e0-aeac-4871-8c60-d026b2833043
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFInterruptObjectRef_9d7e9cb2-6cfd-4b39-82c8-8a29033e390a.xml, EVT_WDF_INTERRUPT_DPC, EVT_WDF_INTERRUPT_DPC callback, EvtInterruptDpc, EvtInterruptDpc callback function, kmdf.evtinterruptdpc, wdf.evtinterruptdpc, wdfinterrupt/EvtInterruptDpc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfinterrupt.h
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
req.irql: "(See Remarks section.)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfinterrupt.h
api_name:
-	EvtInterruptDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_INTERRUPT_DPC callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtInterruptDpc</i> event callback function processes interrupt information that the driver's <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback function has stored.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param AssociatedObject [in]

A handle to the framework device object that the driver passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



To register an <i>EvtInterruptDpc</i> callback function, your driver must place the callback function's address in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>.

Drivers typically <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">complete I/O requests</a> in their <i>EvtInterruptDpc</i> callback functions.

The <i>EvtInterruptDpc</i> callback function executes at DISPATCH_LEVEL and must not access <a href="https://msdn.microsoft.com/0b3c1e00-2416-4534-9934-bb05f91c7482">pageable</a> code. If an <i>EvtInterruptDpc</i> callback function must perform operations at IRQL = PASSIVE_LEVEL, it can <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-work-items">use framework work items</a>. 

In KMDF version 1.11 and later, your driver can support <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupts</a> and provide either an <a href="https://msdn.microsoft.com/1A473A08-EA23-4DFE-8B58-EBB4AC977891">EvtInterruptWorkItem</a> or an <i>EvtInterruptDpc</i> callback function. If your driver supports passive-level interrupts and provides an <i>EvtInterruptDpc</i> callback function, the driver cannot acquire the passive-level interrupt lock from within the callback.

Most drivers use a single <i>EvtInterruptDpc</i> callback function for each type of interrupt. If your driver creates multiple <a href="https://msdn.microsoft.com/42736e2d-2482-46b4-bf52-4efe369db40b">framework queue objects</a> for each device, you might consider using a separate <a href="https://msdn.microsoft.com/EB500A4B-3FF1-44B7-A752-9E5446005542">DPC object</a> and <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function for each queue.

To schedule execution of an <i>EvtInterruptDpc</i> callback function, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547371">WdfInterruptQueueDpcForIsr</a> from within the <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback function.

When a driver schedules the execution of an <i>EvtInterruptDpc</i> callback function, the system adds a DPC object to the system's DPC queue. If the system is not executing higher-priority tasks, it removes the object from the queue and calls the <i>EvtInterruptDpc</i> callback function. 

The system does not add the DPC object to the DPC queue if the object is already queued. An <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback function might be called several times before the system calls the <i>EvtInterruptDpc</i> callback function. Therefore, the <i>EvtInterruptDpc</i> callback function must be able to process information from several interrupts, and it must process all interrupts that have occurred since the last time it was called.

Typically, it is necessary to synchronize the execution of a driver's <i>EvtInterruptDpc</i> callback function with the execution of other callback functions. For more information, see <a href="https://msdn.microsoft.com/a24477dc-f75d-4ab6-8695-d8a85247e276">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

To define an <i>EvtInterruptDpc</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtInterruptDpc</i> callback function that is named <i>MyInterrruptDpc</i>, use the <b>EVT_WDF_INTERRUPT_DPC</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_INTERRUPT_DPC MyInterruptDpc;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyInterruptDpc (
    WDFINTERRUPT  Interrupt,
    WDFOBJECT  AssociatedObject
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_INTERRUPT_DPC</b> function type is defined in the Wdfinterrupt.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_INTERRUPT_DPC</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a>



<a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547371">WdfInterruptQueueDpcForIsr</a>
 

 

