---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_SYNCHRONIZE
title: EVT_WDF_INTERRUPT_SYNCHRONIZE (wdfinterrupt.h)
description: A driver's EvtInterruptSynchronize event callback function performs operations that must be synchronized with an EvtInterruptIsr callback function.
old-location: wdf\evtinterruptsynchronize.htm
tech.root: wdf
ms.assetid: ac73b23d-7742-43a4-8950-b301bd0ba330
ms.date: 02/26/2018
ms.keywords: DFInterruptObjectRef_4310d770-645e-48c8-bd33-b9edcc8cb667.xml, EVT_WDF_INTERRUPT_SYNCHRONIZE, EVT_WDF_INTERRUPT_SYNCHRONIZE callback, EvtInterruptSynchronize, EvtInterruptSynchronize callback function, kmdf.evtinterruptsynchronize, wdf.evtinterruptsynchronize, wdfinterrupt/EvtInterruptSynchronize
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
-	EvtInterruptSynchronize
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_INTERRUPT_SYNCHRONIZE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtInterruptSynchronize</i> event callback function performs operations that must be synchronized with an <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback function.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param Context [in]

Driver-supplied information that the driver specifies when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547389">WdfInterruptSynchronize</a>.


## -returns



The <i>EvtInterruptSynchronize</i> callback function must return <b>TRUE</b> if the operation succeeds. Otherwise, this function must return <b>FALSE</b>. 




## -remarks



To execute an <i>EvtInterruptSynchronize</i> callback function, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547389">WdfInterruptSynchronize</a>. 

If the driver has configured the interrupt object for handling at the device's IRQL (DIRQL), then before calling the <i>EvtInterruptSynchronize</i> callback function, the framework raises the processor's interrupt request level to DIRQL and acquires the spin lock that the driver specified in the interrupt object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure. 

As a result, while an <i>EvtInterruptSynchronize</i> callback function is executing, the interrupt object's <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback function (and any other code that executes at DIRQL while holding the spin lock) cannot execute. 

<i>EvtInterruptSynchronize</i> callback functions must be designed so that they execute for only a short period of time. They are typically used to access interrupt data that is also accessed by an interrupt object's other <i>EvtInterruptSynchronize</i> or <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback functions. 

Beginning with version 1.11 of KMDF, your driver can provide <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver has requested passive-level interrupt handling, then before calling the <i>EvtInterruptSynchronize</i> function at IRQL = PASSIVE_LEVEL, the framework acquires the passive-level interrupt lock that the driver configured in the interrupt object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure.

For more information about the <i>EvtInterruptSynchronize</i> callback function, see <a href="https://msdn.microsoft.com/a24477dc-f75d-4ab6-8695-d8a85247e276">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

To define an <i>EvtInterruptSynchronize</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtInterruptSynchronize</i> callback function that is named <i>MyInterruptSynchronize</i>, use the <b>EVT_WDF_INTERRUPT_SYNCHRONIZE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_INTERRUPT_SYNCHRONIZE  MyInterruptSynchronize;</pre>
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
BOOLEAN
 MyInterruptSynchronize (
    WDFINTERRUPT  Interrupt,
    WDFCONTEXT  Context
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_INTERRUPT_SYNCHRONIZE</b> function type is defined in the Wdfinterrupt.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_INTERRUPT_SYNCHRONIZE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547389">WdfInterruptSynchronize</a>
 

 

