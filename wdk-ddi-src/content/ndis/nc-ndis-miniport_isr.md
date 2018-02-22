---
UID: NC:ndis.MINIPORT_ISR
title: MINIPORT_ISR
author: windows-driver-content
description: NDIS calls the MiniportInterrupt function when a NIC, or another device that shares the interrupt with the NIC, generates an interrupt.
old-location: netvista\miniportinterrupt.htm
old-project: netvista
ms.assetid: 810503b9-75cd-4b38-ab1f-de240968ded6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.miniportinterrupt, MiniportInterrupt callback function [Network Drivers Starting with Windows Vista], MiniportInterrupt, MINIPORT_ISR, MINIPORT_ISR, ndis/MiniportInterrupt, ndis_interrupts_miniport_functions_ref_1de81c1c-10f4-4b41-81bf-495192b65f02.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	MiniportInterrupt
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_ISR callback


## -description


NDIS calls the
   <i>MiniportInterrupt</i> function when a NIC, or another device that shares the
   interrupt with the NIC, generates an interrupt.
<div class="alert"><b>Note</b>  You must declare this function by using the <b>MINIPORT_ISR</b> type. For more information,
   see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_ISR MiniportInterrupt;

BOOLEAN MiniportInterrupt(
  _In_  NDIS_HANDLE MiniportInterruptContext,
  _Out_ PBOOLEAN    QueueDefaultInterruptDpc,
  _Out_ PULONG      TargetProcessors
)
{ ... }
````


## -parameters




### -param MiniportInterruptContext [in]

A handle to a block of interrupt context information. The miniport driver supplied this handle in
     the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
     NdisMRegisterInterruptEx</a> function.


### -param QueueDefaultInterruptDpc [out]

A pointer to a BOOLEAN variable that the miniport driver sets before it returns from this call. A
     miniport driver sets this value to <b>TRUE</b> to indicate that the driver requires a DPC on the default
     (current) CPU. If this value is set to <b>TRUE</b>, NDIS ignores the value of the 
     <i>TargetProcessors</i> parameter. If it is  set to <b>FALSE</b>, NDIS uses the value of the 
     <i>TargetProcessors</i> parameter to schedule DPCs. If 
     <i>QueueDefaultInterruptDpc</i> is <b>TRUE</b>, NDIS will schedule a DPC regardless of the
     return value from 
     <i>MiniportInterrupt</i>.


### -param TargetProcessors [out]

A bitmask that indicates the target processors for which NDIS should schedule a DPC. This bitmask represents the first 32 processors in processor group 0. Each bit in 
     the bitmask identifies a CPU. If the caller sets bit 0, NDIS schedules a DPC for CPU 0. If the caller sets bit 1, NDIS
     schedules a DPC for CPU 1, and so on. If 
     <i>QueueDefaultInterruptDpc</i> is set to <b>FALSE</b> and 
     <i>TargetProcessors</i> is set to zero, NDIS will not schedule any DPCs. Otherwise,
     NDIS will schedule DPCs regardless of the return value from 
     <i>MiniportInterrupt</i>.

<div class="alert"><b>Note</b>  NDIS
     6.20 and later drivers should not use this parameter to schedule DPCs. Instead, they should set this parameter to zero and use the 
     <a href="..\ndis\nf-ndis-ndismqueuedpcex.md">NdisMQueueDpcEx</a> function to schedule DPCs.</div>
<div> </div>

## -returns



<i>MiniportInterrupt</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>TRUE</b></b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> determined that the underlying NIC generated the
       interrupt.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>FALSE</b></b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> determined that the underlying NIC did not generate the
       interrupt.

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  NDIS will queue DPCs based on the values that are specified in the 
      <i>QueueDefaultInterruptDpc</i> and 
      <i>TargetProcessors</i> parameters regardless of the value that 
      <i>MiniportInterrupt</i> returns. However, 
      <i>MiniportInterrupt</i> must still return the correct value.</div>
<div> </div>



## -remarks



Miniport drivers that register an interrupt with the 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a> function
    must provide a 
    <i>MiniportInterrupt</i> function.

A miniport driver should do as little work as possible in its 
    <i>MiniportInterrupt</i> function. It should defer I/O operations for the interrupts
    that the NIC generates to the 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function.

When an interrupt occurs on a NIC's interrupt line, NDIS calls the miniport driver's 
    <i>MiniportInterrupt</i> function.

All NICs can share line-based interrupts with other devices on the I/O bus. If the NIC did not
    generate the interrupt, 
    <i>MiniportInterrupt</i> should return <b>FALSE</b> immediately so that the system can call
    the driver of the device that generated the interrupt. If the 
    <i>QueueDefaultInterruptDpc</i> is set to <b>FALSE</b> and the 
    <i>TargetProcessors</i> parameter is set to zero, NDIS will not schedule any DPCs.
    Otherwise, NDIS will schedule DPCs egardless of the re<i>MiniportInterrupt</i>turn value from 
    <i>MiniportInterrupt</i>.

If the interrupt is for the NIC,
     <i>MiniportInterrupt</i> dismisses the interrupt on the NIC, saves whatever state it
    must about the interrupt, and defers as much of the I/O processing as possible to the 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function.

If the underlying NIC generated the specified interrupt and the miniport driver will request deferred
    procedure calls (DPCs), the miniport driver should disable all further interrupts from the NIC and
    reenable the interrupts after all the DPCs are finished.

The miniport driver should set 
    <i>QueueDefaultInterruptDpc</i> to <b>TRUE</b> to schedule a DPC for the default CPU only.
    The driver could do this, for example, if:

<ul>
<li>
The NIC generated the interrupt to signal the completion of a send operation, or any other request
      that doesn't run on other CPUs.

</li>
<li>
The NIC generated the interrupt to signal received data and the miniport driver cannot process
      received packets in separate DPCs.

</li>
<li>
The interrupt indicates received packets and the miniport driver can process received packets in
      separate DPCs, but <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-receive-side-scaling2">receive side scaling (RSS)</a> is not enabled for the miniport driver. For more information,
      see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities">
      OID_GEN_RECEIVE_SCALE_CAPABILITIES</a> and 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-receive-scale-parameters">
      OID_GEN_RECEIVE_SCALE_PARAMETERS</a>.

</li>
</ul>
If a miniport driver processes received packets in separate DPCs, the driver sets the 
    <i>QueueDefaultInterruptDpc</i> parameter to <b>FALSE</b>. The miniport driver should set the
    
    <i>TargetProcessors</i> bit for the CPU that is associated with each nonempty receive
    queue. NDIS will schedule a DPC on each of the indicated CPUs.

<div class="alert"><b>Note</b>  NDIS will queue DPCs based on the values that are specified in the 
    <i>QueueDefaultInterruptDpc</i> and 
    <i>TargetProcessors</i> parameters regardless of the value that 
    <i>MiniportInterrupt</i> returns. However, 
    <i>MiniportInterrupt</i> must still return the correct value.</div>
<div> </div>
If 
    <i>MiniportInterrupt</i> shares resources, such as NIC registers or state variables,
    with another 
    <i>MiniportXxx</i> function that runs at a lower IRQL, that 
    <i>MiniportXxx</i> function must call the 
    <a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
    NdisMSynchronizeWithInterruptEx</a> function. This ensures that the driver's 
    <i>MiniportSynchronizeInterrupt</i> function accesses the shared resources in a
    synchronized and multiprocessor-safe manner.

A miniport driver can call the 
    <a href="..\ndis\nf-ndis-ndismderegisterinterruptex.md">
    NdisMDeregisterInterruptEx</a> function from its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> or 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function to release
    resources that it allocated with 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>. After 
    <b>NdisMDeregisterInterruptEx</b> returns, NDIS does not call a miniport
    driver's 
    <i>MiniportInterrupt</i> or 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function.

NDIS calls 
    <i>MiniportInterrupt</i> at the DIRQL of the interrupt that the miniport driver
    registered in a previous call to 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>. Therefore, 
    <i>MiniportInterrupt</i> must call the subset of the NDIS functions, such as the 
    <b>NdisRaw</b><i>Xxx</i> or 
    <b>NdisRead/WriteRegister</b><i>Xxx</i> functions, that are safe to call at any IRQL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportInterrupt</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportInterrupt</i> function that is named "MyInterrupt", use the <b>MINIPORT_ISR</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_ISR MyInterrupt;</pre>
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
 MyInterrupt(
    NDIS_HANDLE  MiniportInterruptContext,
    PBOOLEAN  QueueDefaultInterruptDpc,
    PULONG  TargetProcessors
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_ISR</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ISR</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-receive-side-scaling2">Receive Side Scaling (RSS)</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>



<a href="..\ndis\nf-ndis-ndismderegisterinterruptex.md">NdisMDeregisterInterruptEx</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities">
   OID_GEN_RECEIVE_SCALE_CAPABILITIES</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_interrupt_characteristics.md">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-receive-scale-parameters">
   OID_GEN_RECEIVE_SCALE_PARAMETERS</a>



<a href="..\ndis\nf-ndis-ndismqueuedpcex.md">NdisMQueueDpcEx</a>



<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>



<a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
   NdisMSynchronizeWithInterruptEx</a>



<a href="..\ndis\nc-ndis-miniport_synchronize_interrupt.md">
   MiniportSynchronizeInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_ISR callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

