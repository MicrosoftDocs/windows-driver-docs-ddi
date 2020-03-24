---
UID: NC:ndis.MINIPORT_MESSAGE_INTERRUPT_DPC
title: MINIPORT_MESSAGE_INTERRUPT_DPC (ndis.h)
description: A miniport driver must provide a MiniportMessageInterruptDPC handler if the driver calls the NdisMRegisterInterruptEx function to register an interrupt.
old-location: netvista\miniportmessageinterruptdpc.htm
tech.root: netvista
ms.assetid: c1eca20b-eda1-442c-8644-798fa864d5d7
ms.date: 05/02/2018
keywords: ["MINIPORT_MESSAGE_INTERRUPT_DPC callback function"]
ms.keywords: MINIPORT_MESSAGE_INTERRUPT_DPC, MINIPORT_MESSAGE_INTERRUPT_DPC callback, MiniportMessageInterruptDPC, MiniportMessageInterruptDPC callback function [Network Drivers Starting with Windows Vista], ndis/MiniportMessageInterruptDPC, ndis_interrupts_miniport_functions_ref_eb463565-15ab-4751-be20-4239e6ccb987.xml, netvista.miniportmessageinterruptdpc
f1_keywords:
 - "ndis/MiniportMessageInterruptDPC"
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
- MiniportMessageInterruptDPC
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_MESSAGE_INTERRUPT_DPC callback function


## -description


A miniport driver must provide a
   <i>MiniportMessageInterruptDPC</i> handler if the driver calls the 
   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a> function
   to register an interrupt.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_MESSAGE_INTERRUPT_DPC</b> type. For
   more information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportInterruptContext [in]

A handle to a block of interrupt context information. The miniport driver supplied this handle in
     the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">
     NdisMRegisterInterruptEx</a> function.


### -param MessageId [in]

A message-signaled interrupt (MSI) message identifier. 
     <i>MessageId</i> is an index to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info_entry">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structure inside a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     <b>IO_INTERRUPT_MESSAGE_INFO</b> structure in the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a> function.


### -param MiniportDpcContext [in]

A pointer to a context area that the miniport driver supplied when it called the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismqueuedpcex">NdisMQueueDpcEx</a> or 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismqueuedpc">NdisMQueueDpc</a> function. If NDIS called 
     <i>MiniportMessageInterruptDPC</i> because the miniport driver returned a bitmask in the 
     <i>TargetProcessors</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">
     MiniportMessageInterrupt</a> function, then 
     <i>MiniportDpcContext</i> is <b>NULL</b>.


### -param ReceiveThrottleParameters [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_receive_throttle_parameters">
     NDIS_RECEIVE_THROTTLE_PARAMETERS</a> structure specifies the maximum number of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that a miniport
     driver should indicate in a DPC.

<div class="alert"><b>Note</b>  In NDIS 6.1 and earlier, this parameter is named <i>NdisReserved1</i>, its datatype is <b>PULONG</b>, and it is reserved for NDIS.</div>
<div> </div>

### -param NdisReserved1

Reserved for NDIS.

### -param NdisReserved2 [in]

Reserved for NDIS.

<div class="alert"><b>Note</b>  In NDIS 6.1 and earlier, this parameter's datatype is <b>PULONG</b>.</div>
<div> </div>

## -remarks



Miniport drivers that register a message-signaled interrupt with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a> function
    must provide a 
    <i>MiniportMessageInterruptDPC</i> function.

NDIS calls 
    <i>MiniportMessageInterruptDPC</i> to complete the deferred processing of an interrupt. The miniport
    driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismqueuedpcex">NdisMQueueDpcEx</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismqueuedpc">NdisMQueueDpc</a> function to request additional
    deferred procedure calls (DPCs) for other processors.

Miniport drivers determine the source of each interrupt and take appropriate action. For example, if
    an interrupt indicates the completion of a transmit operation, the miniport driver completes a pending
    send request. If the cause of the interrupt is a change in link state, the miniport driver indicates the
    new link status to NDIS. If there are outstanding receive packets, the miniport driver indicates the
    packets to NDIS.

A miniport driver that supports <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-receive-side-scaling2">receive side scaling (RSS)</a>, and has the feature enabled, examines its
    receive queues in 
    <i>MiniportMessageInterruptDPC</i>. The NIC could have already queued received packets on separate queues
    based on hash values, if the NIC provides such capabilities. Otherwise, the miniport driver can sort the
    packets into separate queues in 
    <i>MiniportMessageInterruptDPC</i>.

<i>MiniportMessageInterruptDPC</i> calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
    NdisMIndicateReceiveNetBufferLists</a> function to indicate the packets on the current processor. 
    <i>MiniportMessageInterruptDPC</i> can determine processing that is required for other CPUs and request
    NDIS to schedule DPCs on CPUs where a DPC is not outstanding.

If the current DPC is running on the same CPU as the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">
    MiniportMessageInterrupt</a> function, the miniport driver should indicate all of the packets that
    could not be mapped to a CPU. If this DPC is the last scheduled DPC and it will not request additional
    DPCs, 
    <i>MiniportMessageInterruptDPC</i> should reenable the interrupts on the NIC, for the specified message,
    before it returns.

Before NDIS calls 
    <i>MiniportMessageInterruptDPC</i>, interrupts for the specified message on the NIC, have typically been
    disabled in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">
    MiniportMessageInterrupt</a> function. Before it returns control, 
    <i>MiniportMessageInterruptDPC</i> can reenable interrupts. If the miniport driver queued additional DPCs
    while interrupts were disabled, the driver should enable the interrupts after the last DPC executes.

<div class="alert"><b>Note</b>  For better performance, miniport drivers should only disable interrupts for
    specific messages. They should not disable all message-signaled interrupts.</div>
<div> </div>
Miniport drivers should limit the number of the receive buffers that they indicate while they are
    processing an 
    <i>interrupt DPC batch</i> to complete within the required time limit. An interrupt DPC batch is the
    collection of all the DPCs that run after the ISR and before the interrupts are reenabled.

A miniport driver can call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterinterruptex">NdisMDeregisterInterruptEx</a> from
    its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function to release
    resources that it allocated with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a>. After 
    <b>NdisMDeregisterInterruptEx</b> returns, NDIS does not call a miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">MiniportMessageInterrupt</a> or 
    <i>MiniportMessageInterruptDPC</i> function.

NDIS calls 
    <i>MiniportMessageInterruptDPC</i> at IRQL = DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportMessageInterruptDPC</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportMessageInterruptDPC</i> function that is named "MyMessageInterruptDPC", use the <b>MINIPORT_MESSAGE_INTERRUPT_DPC</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_MESSAGE_INTERRUPT_DPC MyMessageInterruptDPC;</pre>
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
 MyMessageInterruptDPC(
    NDIS_HANDLE  MiniportInterruptContext,
    ULONG  MessageId,
    PVOID  MiniportDpcContext,
    PVOID  ReceiveThrottleParameters,
    PVOID  NdisReserved2
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_MESSAGE_INTERRUPT_DPC</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_MESSAGE_INTERRUPT_DPC</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info_entry">
   IO_INTERRUPT_MESSAGE_INFO_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">MiniportMessageInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_interrupt_characteristics">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_receive_throttle_parameters">
     NDIS_RECEIVE_THROTTLE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterinterruptex">NdisMDeregisterInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismqueuedpc">NdisMQueueDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismqueuedpcex">NdisMQueueDpcEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-receive-side-scaling2">Receive Side Scaling (RSS)</a>
 

 

