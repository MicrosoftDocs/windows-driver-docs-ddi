---
UID: NC:ndis.MINIPORT_PAUSE
title: MINIPORT_PAUSE
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportPause function to stop the flow of network data through a specified miniport adapter.
old-location: netvista\miniportpause.htm
old-project: netvista
ms.assetid: 047241a5-6f52-4a82-a334-8508f0de5e1a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
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
req.alt-api: MiniportPause
req.alt-loc: Ndis.h
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
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_PAUSE callback



## -description
NDIS calls a miniport driver's 
   <i>MiniportPause</i> function to stop the flow of network data through a specified miniport adapter.



## -prototype

````
MINIPORT_PAUSE MiniportPause;

NDIS_STATUS MiniportPause(
  _In_ NDIS_HANDLE                     MiniportAdapterContext,
  _In_ PNDIS_MINIPORT_PAUSE_PARAMETERS MiniportPauseParameters
)
{ ... }
````


## -parameters

### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for an miniport adapter.


### -param MiniportPauseParameters [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_miniport_pause_parameters.md">
     NDIS_MINIPORT_PAUSE_PARAMETERS</a> structure that defines the pause parameters for the miniport
     adapter.


## -returns
<i>MiniportPause</i> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><i>MiniportPause</i> successfully stopped the flow of network data through the miniport adapter.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl><i>MiniportPause</i> did not complete the pause operation and the operation will be completed
       asynchronously. The miniport driver must call the 
       <a href="..\ndis\nf-ndis-ndismpausecomplete.md">NdisMPauseComplete</a> function when the
       operation is complete.

 


## -remarks
A driver specifies the 
    <i>MiniportPause</i> entry point when it calls the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function.

NDIS pauses a miniport adapter to stop data flow that could interfere with PnP operations such as
    adding or removing a filter driver, or binding or unbinding a protocol driver.

NDIS calls a miniport driver's 
    <i>MiniportPause</i> function to initiate a pause request for the miniport adapter specified at 
    <i>MiniportAdapterContext</i>. The miniport adapter remains in the 
    <i>Pausing</i> state until the pause operation is complete.

For a miniport adapter in the 
    <i>Pausing</i> state, the miniport driver:

Waits for all calls to the 
      <a href="..\ndis\nf-ndis-ndismindicatereceivenetbufferlists.md">
      NdisMIndicateReceiveNetBufferLists</a> function to return.

Waits for NDIS to return the ownership of all 
      <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures from
      outstanding receive indications to the miniport driver's 
      <a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
      MiniportReturnNetBufferLists</a> function.

Completes all outstanding send requests and calls the 
      <a href="..\ndis\nf-ndis-ndismsendnetbufferlistscomplete.md">
      NdisMSendNetBufferListsComplete</a> function for all the outstanding send requests.

Rejects all new send requests made to its 
      <a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">
      MiniportSendNetBufferLists</a> function immediately by calling 
      <b>NdisMSendNetBufferListsComplete</b>. It should set the complete status in each NET_BUFFER_LIST to
      NDIS_STATUS_PAUSED.

Can provide status indications with the 
      <a href="..\ndis\nf-ndis-ndismindicatestatusex.md">
      NdisMIndicateStatusEx</a> function.

Should handle OID requests in the 
      <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

Should not stop the miniport adapter completely if stopping the miniport adapter prevents the driver
      from handling requests or providing status indications.

Should not free the resources the driver allocated during initialization.

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
    <a href="..\ndis\nf-ndis-ndismpausecomplete.md">NdisMPauseComplete</a> function. After the
    pause operation is complete, the miniport adapter is in the 
    <i>Paused</i> state.

For a miniport adapter in the 
    <i>Paused</i> state, the miniport driver:

Must reject all send requests made to 
      <i>MiniportSendNetBufferLists</i> immediately by calling 
      <b>NdisMSendNetBufferListsComplete</b>. It should set the Status member in each NET_BUFFER_LIST to
      NDIS_STATUS_PAUSED.

Can handle receive interrupts (see the 
      <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function) and
      interrupt DPCs (see the 
      <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function),
      but should not indicate received network data.

Can provide status indications with the 
      <b>NdisMIndicateStatusEx</b> function.

Should handle OID requests in the 
      <i>MiniportOidRequest</i> function.

Should handle requests to change the device power state in the 
      <a href="..\ndis\nc-ndis-miniport_device_pnp_event_notify.md">
      MiniportDevicePnPEventNotify</a> function.

Can handle calls to 
      <a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a> functions.

Can handle requests to reset the hardware in the 
      <a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> function.

Miniport drivers cannot fail a pause request. Therefore, if a miniport driver requires any resources
    to handle a pause request, it should preallocate the resources during initialization.

NDIS calls the 
    <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> function to initiate a
    restart request for a miniport adapter that is paused.

NDIS calls 
    <i>MiniportPause</i> at IRQL = PASSIVE_LEVEL.

To define a <i>MiniportPause</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportPause</i> function that is named "MyPause", use the <b>MINIPORT_PAUSE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_PAUSE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_PAUSE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_device_pnp_event_notify.md">
   MiniportDevicePnPEventNotify</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
   MiniportReturnNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">MiniportSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_pause_parameters.md">
   NDIS_MINIPORT_PAUSE_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismindicatereceivenetbufferlists.md">
   NdisMIndicateReceiveNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismindicatestatusex.md">NdisMIndicateStatusEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismpausecomplete.md">NdisMPauseComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsendnetbufferlistscomplete.md">
   NdisMSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_PAUSE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

