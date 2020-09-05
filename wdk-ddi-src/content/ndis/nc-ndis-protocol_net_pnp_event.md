---
UID: NC:ndis.PROTOCOL_NET_PNP_EVENT
title: PROTOCOL_NET_PNP_EVENT (ndis.h)
description: NDIS calls the ProtocolNetPnPEvent function to indicate a network Plug and Play event, an NDIS PnP event, or a power management event to a protocol driver.Note  You must declare the function by using the PROTOCOL_NET_PNP_EVENT type.
old-location: netvista\protocolnetpnpevent.htm
tech.root: netvista
ms.assetid: 3f50bcba-c7d2-4d81-bd8b-6080e08fbe74
ms.date: 05/02/2018
keywords: ["PROTOCOL_NET_PNP_EVENT callback function"]
ms.keywords: PROTOCOL_NET_PNP_EVENT, PROTOCOL_NET_PNP_EVENT callback, ProtocolNetPnPEvent, ProtocolNetPnPEvent callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolNetPnPEvent, netvista.protocolnetpnpevent, protocol_functions_ref_24f290b7-d0fc-4d50-9aff-f40f4847a451.xml
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
 - PROTOCOL_NET_PNP_EVENT
 - ndis/PROTOCOL_NET_PNP_EVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - ProtocolNetPnPEvent
---

# PROTOCOL_NET_PNP_EVENT callback function


## -description

NDIS calls the 
  <i>ProtocolNetPnPEvent</i> function to indicate a network Plug and Play event, an NDIS
  PnP event, or a power management event to a protocol driver.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_NET_PNP_EVENT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param ProtocolBindingContext 

[in]
The handle to a protocol-driver-allocated context area in which this driver maintains per-binding
     run-time state information. The protocol driver supplied this handle when it called the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function. A 
     <b>NetEvent</b><i>Xxx</i> event that is indicated with a <b>NULL</b><i>ProtocolBindingContext</i> applies to all bindings. 
     <b>NetEventBindList</b> and 
     <b>NetEventBindsComplete</b> are always indicated with a <b>NULL</b><i>ProtocolBindingContext</i>. 
     <b>NetEventReconfigure</b> can be indicated with a specified 
     <i>ProtocolBindingContext</i> or with a <b>NULL</b><i>ProtocolBindingContext</i>.

### -param NetPnPEventNotification

#### - NetPnPEvent [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">
     NET_PNP_EVENT_NOTIFICATION</a> structure which describes the Plug and Play event or Power Management
     event that NDIS is indicating to the protocol driver.

## -returns

<i>ProtocolNetPnPEvent</i> can return any of the following:

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
The protocol driver successfully handled the indicated network Plug and Play event, NDIS PnP
       event, or power management event. The meaning of this status code depends on the 
       <b>NetEvent</b> code in the buffered 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">
       NET_PNP_EVENT_NOTIFICATION</a> structure at 
       <i>NetPnPEvent</i>:
       



<dl>
<dt><a id="NetEventSetPower"></a><a id="neteventsetpower"></a><a id="NETEVENTSETPOWER"></a><b>NetEventSetPower</b></dt>
<dd>
The protocol driver has performed any driver-specific actions that are required to prepare for
         the device's transition to the requested device power state.

</dd>
<dt><a id="NetEventQueryPower"></a><a id="neteventquerypower"></a><a id="NETEVENTQUERYPOWER"></a><b>NetEventQueryPower</b></dt>
<dd>
The underlying adapter can transition to the requested device power state.

</dd>
<dt><a id="NetEventQueryRemoveDevice"></a><a id="neteventqueryremovedevice"></a><a id="NETEVENTQUERYREMOVEDEVICE"></a><b>NetEventQueryRemoveDevice</b></dt>
<dd>
The underlying adapter can be removed.

</dd>
<dt><a id="NetEventCancelRemoveDevice"></a><a id="neteventcancelremovedevice"></a><a id="NETEVENTCANCELREMOVEDEVICE"></a><b>NetEventCancelRemoveDevice</b></dt>
<dd>
The protocol driver has performed any driver-specific actions that are required to prepare for
         the canceled removal of the underlying adapter.

</dd>
<dt><a id="NetEventReconfigure"></a><a id="neteventreconfigure"></a><a id="NETEVENTRECONFIGURE"></a><b>NetEventReconfigure</b></dt>
<dd>
The protocol driver has accepted the changed configuration.

</dd>
<dt><a id="NetEventBindList"></a><a id="neteventbindlist"></a><a id="NETEVENTBINDLIST"></a><b>NetEventBindList</b></dt>
<dd>
The protocol driver has the new bind list and has performed related processing.

</dd>
<dt><a id="NetEventBindsComplete"></a><a id="neteventbindscomplete"></a><a id="NETEVENTBINDSCOMPLETE"></a><b>NetEventBindsComplete</b></dt>
<dd>
The protocol driver has acknowledged the indication from NDIS that the protocol driver is
         bound to all available underlying adapters.

</dd>
<dt><a id="NetEventPnPCapabilities"></a><a id="neteventpnpcapabilities"></a><a id="NETEVENTPNPCAPABILITIES"></a><b>NetEventPnPCapabilities</b></dt>
<dd>
The protocol driver has acknowledged that it has received the current wake-up capabilities of
         the underlying adapter that is associated with the specified binding.

</dd>
<dt><a id="NetEventPause"></a><a id="neteventpause"></a><a id="NETEVENTPAUSE"></a><b>NetEventPause</b></dt>
<dd>
The specified protocol binding has entered the 
         <i>Pausing</i> state. The binding will enter the 
         <i>Paused</i> state after NDIS has completed all of the outstanding send requests
         for the binding. For more information about pause operations, see 
         <a href="https://docs.microsoft.com/windows-hardware/drivers/network/pausing-a-binding">Pausing a Binding</a>.

</dd>
<dt><a id="NetEventRestart"></a><a id="neteventrestart"></a><a id="NETEVENTRESTART"></a><b>NetEventRestart</b></dt>
<dd>
The specified protocol binding has entered the 
         <i>Restarting</i> state. After the protocol driver is ready to resume send and
         receive operations for the binding, the binding enters the 
         <i>Running</i> state.

</dd>
<dt><a id="NetEventPortActivation"></a><a id="neteventportactivation"></a><a id="NETEVENTPORTACTIVATION"></a><b>NetEventPortActivation</b></dt>
<dd>
The protocol driver has acknowledged the activation of a port that is associated with the
         specified binding. For more information about port activation, see 
         <a href="https://docs.microsoft.com/windows-hardware/drivers/network/activating-an-ndis-port">Activating an NDIS Port</a>.

</dd>
<dt><a id="NetEventPortDeactivation"></a><a id="neteventportdeactivation"></a><a id="NETEVENTPORTDEACTIVATION"></a><b>NetEventPortDeactivation</b></dt>
<dd>
The protocol driver has acknowledged the activation of a port that is associated with the
         specified binding.

</dd>
</dl>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The protocol driver will return its response to the indicated event asynchronously with a call
       to the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompletenetpnpevent">
       NdisCompleteNetPnPEvent</a> function.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The protocol driver could not obtain the necessary system resources to satisfy the indicated
       Plug and Play or Power Management event.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
NDIS 6.0 and later protocol drivers must not return this status. An NDIS 5.<i>x</i> protocol driver that does
       not support Plug and Play can return this status in response to a 
       <b>NetEventSetPower</b> to indicate that NDIS should unbind it from the
       underlying adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The protocol driver failed the indicated event for reasons other than those stated in the
       preceding list.

</td>
</tr>
</table>
 

A protocol driver can fail the 
      <b>NetEventQueryRemoveDevice</b> 
      and 
      <b>NetEventPortActivation</b> events.

If a protocol driver fails the 
      <b>NetEventPortActivation</b> event, it should not use any associated ports in
      subsequent operations.

A protocol driver should always succeed the 
      <b>NetEventRestart</b>, <b>NetEventIMReEnableDevice</b>, 
      <b>NetEventCancelRemoveDevice</b>, 
      <b>NetEventReconfigure</b>, 
      <b>NetEventBindList</b>, 
      <b>NetEventBindsComplete</b>, 
      <b>NetEventPause</b>, <b>NetEventPortDeactivation</b>, and 
      <b>NetEventPnPCapabilities</b> events by returning NDIS_STATUS_SUCCESS.

## -remarks

The 
    <i>ProtocolNetPnPEvent</i> function is required in protocol drivers to support Plug
    and Play and Power Management. NDIS calls 
    <i>ProtocolNetPnPEvent</i> to notify a protocol driver that a network Plug and Play
    event, an NDIS PnP event, or Power Management event has occurred.

The 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">
    NET_PNP_EVENT_NOTIFICATION</a> structure that is passed to 
    <i>ProtocolNetPnPEvent</i> describes the event. 
    <i>ProtocolNetPnPEvent</i> interprets two basic pieces of information in the
    NET_PNP_EVENT_NOTIFICATION structure:

<ul>
<li>
A code in the 
      <b>NetEvent</b> member that identifies the type of Plug and Play or Power
      Management event.

</li>
<li>
Event-specific information. For example, with a 
      <b>NetEventSetPower</b> event the 
      <b>Buffer</b> member contains the device power state to which the device is
      transitioning.

</li>
</ul>
The protocol driver should save the 
    <i>NetPnPEvent</i> pointer. This pointer is a required input parameter to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompletenetpnpevent">NdisCompleteNetPnPEvent</a> function,
    which the protocol driver must subsequently call if 
    <i>ProtocolNetPnPEvent</i> returns NDIS_STATUS_PENDING.

A protocol driver should always succeed a 
    <b>NetEventQueryPower</b> event. After establishing an active connection, a
    protocol driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poregistersystemstate">PoRegisterSystemState</a> function to
    register a continuously busy state. As long as the state registration is in effect, the power manager
    does not attempt to put the system to sleep. After the connection becomes inactive, the protocol driver
    cancels the state registration by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pounregistersystemstate">PoUnregisterSystemState</a> function. A
    protocol driver should never try to prevent the system from transitioning to the sleeping state by
    failing a 
    <b>NetEventQueryPower</b> event. Note that a 
    <b>NetEventQueryPower</b> event is always followed by a 
    <b>NetEventSetPower</b> event. A 
    <b>NetEventSetPower</b> event that specifies the underlying device's current power
    state in effect cancels the 
    <b>NetEventQueryPower</b> event.

If a protocol driver cannot release a device (for example, because the device is in use) it must fail
    a 
    <b>NetEventQueryRemoveDevice</b> event by returning NDIS_STATUS_FAILURE.

A protocol driver should always succeed a 
    <b>NetEventCancelRemoveDevice</b>, a 
    <b>NetEventReconfigure</b>, 
    <b>NetEventBindList, NetEventBindsComplete</b>, 
    <b>NetEventPnPCapabilities</b>, 
    <b>NetEventPause</b>, or 
    <b>NetEventPortDeactivation</b> by returning NDIS_STATUS_SUCCESS.

When handling a 
    <b>NetEventReconfigure</b> or a 
    <b>NetEventBindList</b>, a protocol driver should validate the data associated
    with the event. For more information about such data, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">NET_PNP_EVENT_NOTIFICATION</a>.

NDIS calls 
    <i>ProtocolNetPnPEvent</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolNetPnPEvent</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolNetPnPEvent</i> function that is named "MyNetPnPEvent", use the <b>PROTOCOL_NET_PNP_EVENT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_NET_PNP_EVENT MyNetPnPEvent;</pre>
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
NDIS_STATUS
 MyNetPnPEvent(
    NDIS_HANDLE  ProtocolBindingContext,
    PNET_PNP_EVENT_NOTIFICATION  NetPnPEvent
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_NET_PNP_EVENT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_NET_PNP_EVENT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">NET_PNP_EVENT_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompletenetpnpevent">NdisCompleteNetPnPEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poregistersystemstate">PoRegisterSystemState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pounregistersystemstate">PoUnregisterSystemState</a>

