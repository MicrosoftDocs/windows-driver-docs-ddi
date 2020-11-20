---
UID: NC:ndis.MINIPORT_PAUSE
title: MINIPORT_PAUSE (ndis.h)
description: NDIS calls a miniport driver's MiniportPause function to stop the flow of network data through a specified miniport adapter.
old-location: netvista\miniportpause.htm
tech.root: netvista
ms.assetid: 047241a5-6f52-4a82-a334-8508f0de5e1a
ms.date: 05/02/2018
keywords: ["MINIPORT_PAUSE callback function"]
ms.keywords: MINIPORT_PAUSE, MINIPORT_PAUSE callback, MiniportPause, MiniportPause callback function [Network Drivers Starting with Windows Vista], miniport_functions_ref_ff1257db-4c3e-4e0d-8d46-1736567339ba.xml, ndis/MiniportPause, netvista.miniportpause
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MINIPORT_PAUSE
 - ndis/MINIPORT_PAUSE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - MiniportPause
---

# MINIPORT_PAUSE callback function


## -description

NDIS calls a miniport driver's 
   <i>MiniportPause</i> function to stop the flow of network data through a specified miniport adapter.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_PAUSE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportAdapterContext 

[in]
A handle to a context area that the miniport driver allocated in its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for an miniport adapter.

### -param PauseParameters

#### - MiniportPauseParameters 
[in]
A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_pause_parameters">
     NDIS_MINIPORT_PAUSE_PARAMETERS</a> structure that defines the pause parameters for the miniport
     adapter.

## -returns

<i>MiniportPause</i> returns one of the following status values:

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
<i>MiniportPause</i> successfully stopped the flow of network data through the miniport adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
<i>MiniportPause</i> did not complete the pause operation and the operation will be completed
       asynchronously. The miniport driver must call the 
       <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismpausecomplete">NdisMPauseComplete</a> function when the
       operation is complete.

</td>
</tr>
</table>

## -remarks

A driver specifies the 
    <i>MiniportPause</i> entry point when it calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a> function.

NDIS pauses a miniport adapter to stop data flow that could interfere with PnP operations such as
    adding or removing a filter driver, or binding or unbinding a protocol driver.

NDIS calls a miniport driver's 
    <i>MiniportPause</i> function to initiate a pause request for the miniport adapter specified at 
    <i>MiniportAdapterContext</i>. The miniport adapter remains in the 
    <i>Pausing</i> state until the pause operation is complete.

For a miniport adapter in the 
    <i>Pausing</i> state, the miniport driver:

<ul>
<li>
Waits for all calls to the 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
      NdisMIndicateReceiveNetBufferLists</a> function to return.

</li>
<li>
Waits for NDIS to return the ownership of all 
      <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures from
      outstanding receive indications to the miniport driver's 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
      MiniportReturnNetBufferLists</a> function.

</li>
<li>
Completes all outstanding send requests and calls the 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsendnetbufferlistscomplete">
      NdisMSendNetBufferListsComplete</a> function for all the outstanding send requests.

</li>
<li>
Rejects all new send requests made to its 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_send_net_buffer_lists">
      MiniportSendNetBufferLists</a> function immediately by calling 
      <b>NdisMSendNetBufferListsComplete</b>. It should set the complete status in each NET_BUFFER_LIST to
      NDIS_STATUS_PAUSED.

</li>
<li>
Can provide status indications with the 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatestatusex">
      NdisMIndicateStatusEx</a> function.

</li>
<li>
Should handle OID requests in the 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a> function.

</li>
<li>
Should not stop the miniport adapter completely if stopping the miniport adapter prevents the driver
      from handling requests or providing status indications.

</li>
<li>
Should not free the resources the driver allocated during initialization.

</li>
</ul>
NDIS does not initiate other PnP operations for the miniport adapter, such as halt, initialize, power
    change, pause, or a restart requests, while the miniport adapter is in the 
    <i>Pausing</i> state. NDIS can initiate these PnP operations after a miniport adapter is in the 
    <i>Paused</i> state.

After a miniport driver completes all outstanding send requests and NDIS returns all received network
    data structures (from outstanding receive indications), the driver must complete the pause operation. If
    the driver returns NDIS_STATUS_SUCCESS from 
    <i>MiniportPause</i>, the pause operation is complete. If the driver returns NDIS_STATUS_PENDING, the
    miniport adapter can remain in the 
    <i>Pausing</i> state and the pause operation is complete after the driver calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismpausecomplete">NdisMPauseComplete</a> function. After the
    pause operation is complete, the miniport adapter is in the 
    <i>Paused</i> state.

For a miniport adapter in the 
    <i>Paused</i> state, the miniport driver:

<ul>
<li>
Must reject all send requests made to 
      <i>MiniportSendNetBufferLists</i> immediately by calling 
      <b>NdisMSendNetBufferListsComplete</b>. It should set the Status member in each NET_BUFFER_LIST to
      NDIS_STATUS_PAUSED.

</li>
<li>
Can handle receive interrupts (see the 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> function) and
      interrupt DPCs (see the 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a> function),
      but should not indicate received network data.

</li>
<li>
Can provide status indications with the 
      <b>NdisMIndicateStatusEx</b> function.

</li>
<li>
Should handle OID requests in the 
      <i>MiniportOidRequest</i> function.

</li>
<li>
Should handle requests to change the device power state in the 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_device_pnp_event_notify">
      MiniportDevicePnPEventNotify</a> function.

</li>
<li>
Can handle calls to 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a> functions.

</li>
<li>
Can handle requests to reset the hardware in the 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a> function.

</li>
</ul>
Miniport drivers cannot fail a pause request. Therefore, if a miniport driver requires any resources
    to handle a pause request, it should preallocate the resources during initialization.

NDIS calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a> function to initiate a
    restart request for a miniport adapter that is paused.

NDIS calls 
    <i>MiniportPause</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportPause</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportPause</i> function that is named "MyPause", use the <b>MINIPORT_PAUSE</b> type as shown in this code example:


```
MINIPORT_PAUSE MyPause;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
NDIS_STATUS
 MyPause(
    NDIS_HANDLE  MiniportAdapterContext,
    PNDIS_MINIPORT_PAUSE_PARAMETERS  MiniportPauseParameters
    )
  {...}
```

The <b>MINIPORT_PAUSE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_PAUSE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_device_pnp_event_notify">
   MiniportDevicePnPEventNotify</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
   MiniportReturnNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_send_net_buffer_lists">MiniportSendNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_pause_parameters">
   NDIS_MINIPORT_PAUSE_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatestatusex">NdisMIndicateStatusEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismpausecomplete">NdisMPauseComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsendnetbufferlistscomplete">
   NdisMSendNetBufferListsComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a>