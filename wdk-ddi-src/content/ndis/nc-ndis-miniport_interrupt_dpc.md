---
UID: NC:ndis.MINIPORT_INTERRUPT_DPC
title: MINIPORT_INTERRUPT_DPC (ndis.h)
description: A miniport driver must provide a MiniportInterruptDPC function if the driver calls the NdisMRegisterInterruptEx function to register an interrupt.
old-location: netvista\miniportinterruptdpc.htm
tech.root: netvista
ms.assetid: 345715fb-878c-44d8-bf78-f3add10dd02b
ms.date: 05/02/2018
ms.keywords: MINIPORT_INTERRUPT_DPC, MINIPORT_INTERRUPT_DPC callback, MiniportInterruptDPC, MiniportInterruptDPC callback function [Network Drivers Starting with Windows Vista], ndis/MiniportInterruptDPC, ndis_interrupts_miniport_functions_ref_00c0d07c-600c-4a63-bee2-045b66acdd82.xml, netvista.miniportinterruptdpc
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- MiniportInterruptDPC
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_INTERRUPT_DPC callback function


## -description


A miniport driver must provide a
   <i>MiniportInterruptDPC</i> function if the driver calls the 
   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a> function
   to register an interrupt.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_INTERRUPT_DPC</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportInterruptContext [in]

A handle to a block of interrupt context information. The miniport driver supplied this handle in
     the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterinterruptex">
     NdisMRegisterInterruptEx</a> function.


### -param MiniportDpcContext [in]

A pointer to a context area that the miniport driver supplied when it called the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismqueuedpcex">NdisMQueueDpcEx</a> or 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismqueuedpc">NdisMQueueDpc</a> function. If NDIS called 
     <i>MiniportInterruptDPC</i> because the miniport driver returned a bitmask in the 
     <i>TargetProcessors</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> function, 
     <i>MiniportDpcContext</i> is <b>NULL</b>.


### -param ReceiveThrottleParameters [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_receive_throttle_parameters">
     NDIS_RECEIVE_THROTTLE_PARAMETERS</a> structure. This structure specifies the maximum number of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that a miniport
     driver should indicate in a DPC.


### -param NdisReserved2 [in]

Reserved for NDIS.


## -returns



None




## -remarks



Miniport drivers that register an interrupt with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a> function
    must provide a 
    <i>MiniportInterruptDPC</i> function.

NDIS calls 
    <i>MiniportInterruptDPC</i> to complete the deferred processing of an interrupt. The
    miniport driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismqueuedpcex">NdisMQueueDpcEx</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismqueuedpc">NdisMQueueDpc</a> function to request additional
    deferred procedure calls (DPCs) for other processors.

Miniport drivers determine the source of each interrupt and take appropriate action. For example, if
    an interrupt indicates the completion of a transmit operation, the miniport driver completes a pending
    send request. If the source of the interrupt is a change in link state, the miniport driver indicates the
    new link status to NDIS. If there are outstanding receive packets, the miniport driver indicates the
    packets to NDIS.

A miniport driver that supports <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-receive-side-scaling2">receive side scaling (RSS)</a>, and has the feature enabled, examines its receive
    queues in 
    <i>MiniportInterruptDPC</i>. The NIC could have already queued received packets on
    separate queues based on hash values, if the NIC provides such capabilities. Otherwise, the miniport
    driver can sort the packets into separate queues in 
    <i>MiniportInterruptDPC</i>.

<i>MiniportInterruptDPC</i> calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
    NdisMIndicateReceiveNetBufferLists</a> function to indicate packets on the current processor. 
    <i>MiniportInterruptDPC</i> can identify processing that is required for other CPUs
    and request NDIS to schedule DPCs on CPUs where a DPC is not outstanding.

If the current DPC is running on the same CPU as the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> function, the
    miniport driver should indicate all the packets that could not be mapped to a CPU. If this DPC is the
    last scheduled DPC and it will not request additional DPCs, 
    <i>MiniportInterruptDPC</i> should reenable the interrupts on the NIC before it
    returns.

Interrupts are typically disabled already on the NIC in
    the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> function before NDIS calls 
    <i>MiniportInterruptDPC</i>. Before it returns control, 
    <i>MiniportInterruptDPC</i> can reenable interrupts. If the miniport driver queued
    additional DPCs while interrupts were disabled, the driver should enable the interrupts before the last
    DPC returns.

Miniport drivers should limit the number of the receive buffers that they indicate while they are
    processing an 
    <i>interrupt DPC batch</i> to complete within the required time limit. An interrupt
    DPC batch is the collection of all the DPCs that run after the ISR and before the interrupts are
    reenabled.

A miniport driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismderegisterinterruptex">
    NdisMDeregisterInterruptEx</a> function from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function to release
    resources that it allocated with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a>. After 
    <b>NdisMDeregisterInterruptEx</b> returns, NDIS does not call a miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> or 
    <i>MiniportInterruptDPC</i> function.

NDIS calls 
    <i>MiniportInterruptDPC</i> at IRQL = DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportInterruptDPC</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportInterruptDPC</i> function that is named "MyInterruptDPC", use the <b>MINIPORT_INTERRUPT_DPC</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_INTERRUPT_DPC MyInterruptDPC;</pre>
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
VOID
 MyInterruptDPC(
    NDIS_HANDLE  MiniportInterruptContext,
    PVOID  MiniportDpcContext,
    PVOID  ReceiveThrottleParameters,
    PVOID  NdisReserved2
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_INTERRUPT_DPC</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_INTERRUPT_DPC</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_interrupt_characteristics">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_receive_throttle_parameters">
   NDIS_RECEIVE_THROTTLE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismderegisterinterruptex">NdisMDeregisterInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismqueuedpc">NdisMQueueDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismqueuedpcex">NdisMQueueDpcEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-receive-side-scaling2">Receive Side Scaling (RSS)</a>
 

 

