---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_ENABLE
title: EVT_WDF_INTERRUPT_ENABLE
author: windows-driver-content
description: A driver's EvtInterruptEnable event callback function enables a specified hardware interrupt.
old-location: wdf\evtinterruptenable.htm
tech.root: wdf
ms.assetid: 981195e6-6f62-4a6f-9c84-d98f6cd7bab3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFInterruptObjectRef_eb3a90f0-712a-43fe-8d5c-5a29d1df0a62.xml, EVT_WDF_INTERRUPT_ENABLE, EVT_WDF_INTERRUPT_ENABLE callback, EvtInterruptEnable, EvtInterruptEnable callback function, kmdf.evtinterruptenable, wdf.evtinterruptenable, wdfinterrupt/EvtInterruptEnable
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
-	EvtInterruptEnable
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_INTERRUPT_ENABLE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtInterruptEnable</i> event callback function enables a specified hardware interrupt.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param AssociatedDevice [in]

A handle to the framework device object that the driver passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>.


## -returns



The <i>EvtInterruptEnable</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b> if the function encounters no errors. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 




## -remarks



To register an <i>EvtInterruptEnable</i> callback function, your driver must place the callback function's address in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>.

The framework calls the driver's <i>EvtInterruptEnable</i> callback function each time the device enters its working (D0) state. Additionally, a driver can cause the framework to call the <i>EvtInterruptEnable</i> callback function by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547354">WdfInterruptEnable</a>.  Note that most framework-based drivers should not call <b>WdfInterruptEnable</b>, because the framework calls the driver's <i>EvtInterruptEnable</i> callback function each time the device enters its working (D0) state.

Before calling the <i>EvtInterruptEnable</i> callback function, the framework raises the processor's IRQL to the device's DIRQL and acquires the spin lock that the driver specified in the interrupt object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure. 

Beginning with version 1.11 of KMDF, your driver can provide <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver has requested passive-level interrupt handling, then before calling the <i>EvtInterruptEnable</i> function at IRQL = PASSIVE_LEVEL, the framework acquires the passive-level interrupt lock that the driver configured in the interrupt object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure.

After the <i>EvtInterruptEnable</i> callback function returns, the framework calls the driver's <a href="https://msdn.microsoft.com/38d74ce1-9d9d-4da5-a2b3-579048850b28">EvtDeviceD0EntryPostInterruptsEnabled</a> event callback function at IRQL = PASSIVE_LEVEL.

You must not assume that a device will use the same interrupt resources each time the framework calls your driver's <i>EvtInterruptEnable</i> callback function. Sometimes the PnP manager <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/the-pnp-manager-redistributes-system-resources">redistributes system resources</a>, and it might assign new interrupt resources to your device. The driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547367">WdfInterruptGetInfo</a> to determine a device's interrupt resources.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

To define an <i>EvtInterruptEnable</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtInterruptEnable</i> callback function that is named <i>MyInterruptEnable</i>, use the <b>EVT_WDF_INTERRUPT_ENABLE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_INTERRUPT_ENABLE  MyInterruptEnable;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
 MyInterruptEnable (
    WDFINTERRUPT  Interrupt,
    WDFDEVICE  AssociatedDevice
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_INTERRUPT_ENABLE</b> function type is defined in the Wdfinterrupt.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_INTERRUPT_ENABLE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/38d74ce1-9d9d-4da5-a2b3-579048850b28">EvtDeviceD0EntryPostInterruptsEnabled</a>



<a href="https://msdn.microsoft.com/a9d5e3cd-2e95-4ad6-9380-64fe4df9e27f">EvtInterruptDisable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547354">WdfInterruptEnable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547367">WdfInterruptGetInfo</a>
 

 

