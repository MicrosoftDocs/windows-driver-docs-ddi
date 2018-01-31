---
UID: NC:ndis.MINIPORT_RESET
title: MINIPORT_RESET
author: windows-driver-content
description: NDIS calls an NDIS miniport driver's MiniportResetEx function to initiate a reset of a network interface card (NIC). For more information, see Miniport Adapter Check-for-Hang and Reset Operations and Miniport Driver Hardware Reset.
old-location: netvista\miniportresetex.htm
old-project: netvista
ms.assetid: 15f82163-a1b5-4cef-a53e-8a97adb2cd92
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportresetex, MiniportResetEx callback function [Network Drivers Starting with Windows Vista], MiniportResetEx, MINIPORT_RESET, MINIPORT_RESET, ndis/MiniportResetEx, miniport_functions_ref_13afeb89-4956-4a8d-ade8-8d17a4a84128.xml
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	MiniportResetEx
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_RESET callback


## -description


NDIS calls an NDIS miniport driver's 
   <i>MiniportResetEx</i> function to initiate a reset of a network interface card (NIC). For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/miniport-adapter-check-for-hang-and-reset-operations">Miniport Adapter Check-for-Hang and Reset Operations</a> and <a href="https://msdn.microsoft.com/92a469de-396a-4f13-b73d-dc30dd08be7f">Miniport Driver Hardware Reset</a>.
<div class="alert"><b>Note</b>  An NDIS miniport driver may declare this function by using the <b>MINIPORT_RESET</b> type.</div><div> </div>

## -prototype


````
MINIPORT_RESET MiniportResetEx;

NDIS_STATUS MiniportResetEx(
  _In_  NDIS_HANDLE MiniportAdapterContext,
  _Out_ PBOOLEAN    AddressingReset
)
{ ... }
````


## -parameters




#### - MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


#### - AddressingReset [out]

A pointer to a Boolean variable. The miniport driver sets this variable to <b>TRUE</b> if NDIS should call the 
     <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function to
     restore addressing and other configuration settings to the current values. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff546572">Hardware Reset</a>.


## -returns


<i>MiniportResetEx</i> can return one of the following status values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> successfully reset the miniport adapter to an operational state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The driver will complete the reset operation asynchronously by calling the 
       <a href="..\ndis\nf-ndis-ndismresetcomplete.md">NdisMResetComplete</a> function when the
       operation is done.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESET_IN_PROGRESS</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> determined that the miniport adapter was currently being reset, so this call is
       superfluous.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SOFT_ERRORS</b></dt>
</dl>
</td>
<td width="60%">
<i>MiniportResetEx</i> successfully reset the miniport adapter but a recoverable error occurred during
       the operation. 
       <i>MiniportResetEx</i> should have called the 
       <a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a> function
       with more information about the error.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_HARD_ERRORS</b></dt>
</dl>
</td>
<td width="60%">
<i>MiniportResetEx</i> tried to reset the miniport adapter but an unrecoverable error occurred during
       the operation. 
       <i>MiniportResetEx</i> should have called 
       <b>NdisWriteErrorLogEntry</b> with more information about the error.

</td>
</tr>
</table> 



## -remarks


A driver specifies the 
    <i>MiniportResetEx</i> entry point when it calls the 
    <mshelp:link keywords="netvista.ndismregisterminiportdriver" tabindex="0"><b>
    NdisMRegisterMiniportDriver</b></mshelp:link> function.

<i>MiniportResetEx</i> is not required for intermediate drivers.

<i>MiniportResetEx</i> can reset the parameters of the miniport adapter. If a reset causes a change in the
    miniport adapter's station address, the miniport driver automatically restores the prior value of the
    station address after the reset is complete. Any multicast or functional addressing masks, reset by the
    hardware, do not have to be reset in this function.

If a reset operation changes other information, such as multicast or functional addressing
    information, 
    <i>MiniportResetEx</i> must set the variable at 
    <i>AddressingReset</i> to <b>TRUE</b> before it returns. This causes NDIS to call the 
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function to
    restore the information. NDIS also restores the Wake on the LAN (WoL) pattern list by calling 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569773">OID_PNP_ADD_WAKE_UP_PATTERN</a>. The
    driver should free the WoL pattern list from its adapter context because the hardware list is already
    reset.

NDIS will not abort any pending OID requests or send requests. If the driver can safely complete
    pending OID or send requests after a reset, the driver can hold pending OID or send requests until after
    the reset operation is complete. Otherwise, the driver should complete the pending OID or send requests
    by calling the 
    <a href="..\ndis\nf-ndis-ndismoidrequestcomplete.md">NdisMOidRequestComplete</a> or 
    <mshelp:link keywords="netvista.ndismsendnetbufferlistscomplete" tabindex="0"><b>
    NdisMSendNetBufferListsComplete</b></mshelp:link> functions respectively before 
    <i>MiniportResetEx</i> returns.
<div class="alert"><b>Note</b>  Starting with NDIS 6.30, the miniport driver must not hold pending OID or send requests until after
    the reset operation is complete. Instead, the driver must complete these pending requests
    by calling the 
    <a href="..\ndis\nf-ndis-ndismoidrequestcomplete.md">NdisMOidRequestComplete</a> or 
    <a href="..\ndis\nf-ndis-ndismsendnetbufferlistscomplete.md">NdisMSendNetBufferListsComplete</a> functions respectively  before 
    the reset operation is complete. If the driver completes the reset operation asynchronously, it must complete pending OID and send requests before the driver calls <a href="..\ndis\nf-ndis-ndismresetcomplete.md">NdisMResetComplete</a>.</div><div> </div>A miniport driver should not call the 
    <a href="..\ndis\nf-ndis-ndismindicatestatusex.md">NdisMIndicateStatusEx</a> function to
    signal the start and finish of each reset operation. NDIS notifies bound protocol drivers when a reset
    begins and ends.

If 
    <i>MiniportResetEx</i> must wait for state changes in the miniport adapter during reset operations, it can
    call the 
    <a href="..\ndis\nf-ndis-ndisstallexecution.md">NdisStallExecution</a> function. However, a
    
    <i>MiniportResetEx</i> function must not call 
    <b>NdisStallExecution</b> with a time interval larger than 50 microseconds. If the driver must wait longer
    than 50 microseconds (or if would poll), it should set a timer instead and return
    NDIS_STATUS_PENDING.

If 
    <i>MiniportResetEx</i> returns NDIS_STATUS_PENDING, the driver must complete the reset by calling the 
    <a href="..\ndis\nf-ndis-ndismresetcomplete.md">NdisMResetComplete</a> function.

If a miniport adapter is in the 
    <b>MediaConnectStateConnected</b> state and its state changes because of a reset, including a change to
    the 
    <b>MediaConnectStateUnknown</b> state, the miniport driver must report the state change with an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567391">NDIS_STATUS_LINK_STATE</a> status
    indication. The miniport driver must also indicate a 
    <b>MediaConnectStateConnected</b> status indication when the link is reestablished after the reset.

<i>MiniportResetEx</i> can be preempted by an interrupt.

NDIS calls the 
    <a href="..\ndis\nc-ndis-miniport_check_for_hang.md">MiniportCheckForHangEx</a> function
    periodically to determine whether it should call 
    <i>MiniportResetEx</i>. The default time-out for calling 
    <i>MiniportCheckForHangEx</i> is 2 seconds. If this default is too short, a miniport driver can set a larger <b>CheckForHangTimeInSeconds</b> value when calling the
    
    <mshelp:link keywords="netvista.ndismsetminiportattributes" tabindex="0"><b>
    NdisMSetMiniportAttributes</b></mshelp:link> function during initialization. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/miniport-adapter-check-for-hang-and-reset-operations">Miniport Adapter Check-for-Hang and Reset Operations</a>.

NDIS cannot determine whether a NIC has stopped responding for receive operations. To handle this kind
    of failure, the 
    <i>MiniportCheckForHangEx</i> function can monitor receive operations and, if necessary, return <b>TRUE</b> to
    force a reset. A miniport can also request a reset by calling <a href="..\ndis\nf-ndis-ndismresetminiport.md">NdisMResetMiniport</a>.

NDIS calls 
    <i>MiniportResetEx</i> at IRQL &lt;= DISPATCH_LEVEL.
<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>To define a <i>MiniportResetEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportResetEx</i> function that is named "MyResetEx", use the <b>MINIPORT_RESET</b> type as shown in this code example:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_RESET MyResetEx;</pre>
</td>
</tr>
</table></span></div>Then, implement your function as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NDIS_STATUS
 MyResetEx(
    NDIS_HANDLE  MiniportAdapterContext,
    PBOOLEAN  AddressingReset
    )
  {...}</pre>
</td>
</tr>
</table></span></div>The <b>MINIPORT_RESET</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_RESET</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 



## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/miniport-adapter-check-for-hang-and-reset-operations">Miniport Adapter Check-for-Hang and Reset Operations</a>

<a href="..\ndis\nf-ndis-ndismresetminiport.md">NdisMResetMiniport</a>

<a href="https://msdn.microsoft.com/92a469de-396a-4f13-b73d-dc30dd08be7f">Miniport Driver Hardware Reset</a>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="..\ndis\nf-ndis-ndisstallexecution.md">NdisStallExecution</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567391">NDIS_STATUS_LINK_STATE</a>

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>

<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>

<a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndismresetcomplete.md">NdisMResetComplete</a>

<mshelp:link keywords="netvista.ndismsendnetbufferlistscomplete" tabindex="0"><b>
   NdisMSendNetBufferListsComplete</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndismoidrequestcomplete.md">NdisMOidRequestComplete</a>

<a href="..\ndis\nc-ndis-miniport_check_for_hang.md">MiniportCheckForHangEx</a>

<a href="..\ndis\nf-ndis-ndismindicatestatusex.md">NdisMIndicateStatusEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_RESET callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

