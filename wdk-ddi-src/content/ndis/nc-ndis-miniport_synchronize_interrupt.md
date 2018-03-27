---
UID: NC:ndis.MINIPORT_SYNCHRONIZE_INTERRUPT
title: MINIPORT_SYNCHRONIZE_INTERRUPT
author: windows-driver-content
description: A miniport driver must provide a MiniportSynchronizeInterrupt handler if any driver function that runs at less than DIRQL shares resources with the MiniportInterrupt function.
old-location: netvista\miniportsynchronizeinterrupt.htm
old-project: netvista
ms.assetid: aac1ff91-76aa-46a0-8e8a-85b9f8c3323c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "(*MINIPORT_SYNCHRONIZE_INTERRUPT_HANDLER), (*MINIPORT_SYNCHRONIZE_INTERRUPT_HANDLER) callback function [Network Drivers Starting with Windows Vista], MINIPORT_SYNCHRONIZE_INTERRUPT, MiniportSynchronizeInterrupt, MiniportSynchronizeInterrupt callback function [Network Drivers Starting with Windows Vista], ndis/MiniportSynchronizeInterrupt, ndis_interrupts_miniport_functions_ref_68ebc08d-67f9-42d8-9ade-669dc35a4242.xml, netvista.miniportsynchronizeinterrupt"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	(*MINIPORT_SYNCHRONIZE_INTERRUPT_HANDLER)
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_SYNCHRONIZE_INTERRUPT callback


## -description


A miniport driver must provide a 
   <i>MiniportSynchronizeInterrupt</i> handler if any driver function that runs at less than DIRQL shares
   resources with the 
   <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> function.

For message signaled interrupts, the miniport driver provides a <i>MiniportSynchronizeMessageInterrupt</i> handler if any driver function that runs at less than DIRQL shares resources for a message signaled interrupt with the <a href="https://msdn.microsoft.com/ec2e6f49-dc40-48e8-96dc-c9440a6662a3">MiniportMessageInterrupt</a> function.
<div class="alert"><b>Note</b>  You must declare this function by using either the <b>MINIPORT_SYNCHRONIZE_INTERRUPT</b> type for non-message signaled interrupts, or by using the <b>MINIPORT_SYNCHRONIZE_MESSAGE_INTERRUPT</b> type for message signaled interrupts. For
   more information, see the following Examples section.</div><div> </div>

## -parameters




### -param SynchronizeContext [in]

A handle to a context area that is supplied when the miniport driver's 
     <i>MiniportXxx</i> or internal function called the 
     <a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
     NdisMSynchronizeWithInterruptEx</a> function.


## -returns



<i>MiniportSynchronizeInterrupt</i> returns a Boolean value with a driver-determined meaning. NDIS
     returns the same value when NDIS returns from 
     <b>NdisMSynchronizeWithInterruptEx</b>.




## -remarks



<div class="alert"><b>Note</b>  The information in this section can also apply to message signaled interrupts by substituting "MiniportInterrupt" for "MiniportMessageInterrupt," and by substituting "MiniportSynchronizeInterrupt" for "MiniportSynchronizeMessageInterrupt."</div>
<div> </div>
If any miniport driver function that runs at less than DIRQL shares resources, such as NIC registers,
    with the driver's 
    <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> function, that
    driver cannot access those resources directly. If such a lower priority function attempts to access the
    shared resources directly, it might be preempted by 
    <i>MiniportInterrupt</i>, which could override the state changes of the lower priority driver function.

To synchronize access to shared resources with 
    <i>MiniportInterrupt</i>, lower priority driver functions must call the 
    <a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
    NdisMSynchronizeWithInterruptEx</a> function. The driver's 
    <i>MiniportSynchronizeInterrupt</i> function accesses the shared resources at DIRQL. Calling 
    <b>NdisMSynchronizeWithInterruptEx</b> prevents race conditions and deadlocks in such a miniport
    driver.

Any lower priority driver functions that share resources among themselves (but not with any function
    that runs at DIRQL) should use a spin lock to protect those shared resources.

<i>MiniportSynchronizeInterrupt</i> runs at the DIRQL assigned when the driver's 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function
    calls the 
    <a href="https://msdn.microsoft.com/db0b3d51-5bbb-45fb-8c45-dda8c2212b5f">
    NdisMRegisterInterruptEx</a> function. Like any driver function that runs at DIRQL, 
    <i>MiniportSynchronizeInterrupt</i> should return control back to the caller as quickly as possible, and
    it can call only those 
    <b>Ndis<i>Xxx</i></b> functions that are safe to call at any IRQL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportSynchronizeInterrupt</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportSynchronizeInterrupt</i> function that is named "MySynchronizeInterrupt", use the <b>MINIPORT_SYNCHRONIZE_INTERRUPT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_SYNCHRONIZE_INTERRUPT MySynchronizeInterrupt;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
BOOLEAN
 MySynchronizeInterrupt(
    NDIS_HANDLE  SynchronizeContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
To define a <i>MiniportSynchronizeMessageInterrupt</i> function for message signaled interrupts, use the <b>MINIPORT_SYNCHRONIZE_MESSAGE_INTERRUPT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_SYNCHRONIZE_MESSAGE_INTERRUPT MySynchronizeMessageInterrupt;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
BOOLEAN
 MySynchronizeMessageInterrupt(
    NDIS_HANDLE  SynchronizeContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_SYNCHRONIZE_INTERRUPT</b> and <b>MINIPORT_SYNCHRONIZE_MESSAGE_INTERRUPT</b> function types are defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definitions.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInetrrupt</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563649">NdisMRegisterInterruptEx</a>



<a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
   NdisMSynchronizeWithInterruptEx</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_SYNCHRONIZE_INTERRUPT callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

