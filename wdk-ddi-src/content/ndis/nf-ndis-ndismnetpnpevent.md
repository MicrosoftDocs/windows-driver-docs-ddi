---
UID: NF:ndis.NdisMNetPnPEvent
title: NdisMNetPnPEvent function
author: windows-driver-content
description: NDIS miniport drivers (and intermediate drivers that are registered as miniport drivers) call the NdisMNetPnPEvent function to originate a network Plug and Play event, an NDIS PnP event, or Power Management event or propagate it to overlying drivers.
old-location: netvista\ndismnetpnpevent.htm
old-project: netvista
ms.assetid: cbb097c1-dd20-4c6d-b23a-1e7683ac3e94
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisMNetPnPEvent, NdisMNetPnPEvent function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_0f39567c-b58c-438e-936e-36323bbc2ea6.xml, ndis/NdisMNetPnPEvent, netvista.ndismnetpnpevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function, NdisMNetPnPEventInOIDRequest
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMNetPnPEvent
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMNetPnPEvent function


## -description


NDIS miniport drivers (and intermediate drivers that are registered as miniport drivers) call the 
  <b>NdisMNetPnPEvent</b> function to originate a network Plug and Play event, an NDIS PnP event,
  or Power Management event or propagate it to overlying drivers.


## -syntax


````
NDIS_STATUS NdisMNetPnPEvent(
  _In_ NDIS_HANDLE                 MiniportAdapterHandle,
  _In_ PNET_PNP_EVENT_NOTIFICATION NetPnPEvent
);
````


## -parameters




### -param MiniportAdapterHandle [in]

An NDIS handle which NDIS provided at the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     This handle identifies the miniport adapter that is affected by the event. If the caller is an
     intermediate driver, this is the handle of the virtual miniport.


### -param NetPnPEventNotification

TBD




#### - NetPnPEvent [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_pnp_event_notification.md">
     NET_PNP_EVENT_NOTIFICATION</a> structure, which describes the network Plug and Play event, NDIS PnP
     event, or Power Management event.


## -returns



<b>NdisMNetPnPEvent</b> can return the following:

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
The overlying drivers successfully processed the Plug and Play or Power Management event.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The overlying drivers could not obtain the necessary system resources to satisfy the indicated
       Plug and Play or Power Management event.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
NDIS failed the call because some of the input parameters are invalid.

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
       <b>NetEventSetPower</b> to indicate that NDIS should unbind it from the underlying adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PORT</b></dt>
</dl>
</td>
<td width="60%">
NDIS failed the request because an invalid NDIS port was specified in a 
       <b>NetEventPortActivation</b> or 
       <b>NetEventPortDeactivation</b> PnP event.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PORT_STATE</b></dt>
</dl>
</td>
<td width="60%">
NDIS failed the request because an NDIS port was in an invalid port state. The ports are
       specified in a 
       <b>NetEventPortActivation</b> or 
       <b>NetEventPortDeactivation</b> PnP event.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The overlying drivers' attempts to process the propagated Plug and Play or Power Management
       event failed.

</td>
</tr>
</table>
 

The return value is significant only when the propagated event is a 
      <b>NetEventQueryPower</b> or 
      <b>NetEventQueryRemoveDevice</b> event. For all other propagated events, the return value is always
      NDIS_STATUS_SUCCESS.

If the event is 
      <b>NetEventPortActivation</b> and the call fails, the caller should not use the associated ports in
      receive indications or status indications.




## -remarks



Any miniport driver can call 
    <b>NdisMNetPnPEvent</b> to generate 
    <b>NetEventPortActivation</b> and 
    <b>NetEventPortDeactivation</b> events. Only intermediate drivers can make other event notifications.

<div class="alert"><b>Note</b>  To prevent deadlocks, an NDIS driver must do the following:<ul>
<li>Its <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function must not call 
    <b>NdisMNetPnPEvent</b>.</li>
<li> If its <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function returns NDIS_STATUS_PENDING for an OID request, the NDIS driver must not call 
    <b>NdisMNetPnPEvent</b> until after it has completed the OID request by calling <a href="..\ndis\nf-ndis-ndismoidrequestcomplete.md">NdisMOidRequestComplete</a>.</li>
</ul>
</div>
<div> </div>
To propagate notification of a network Plug and Play event, an NDIS PnP event, or Power Management
    event to overlying drivers, an NDIS intermediate driver calls 
    <b>NdisMNetPnPEvent</b> in the context of the driver's 
    <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function.

If the propagated event is a 
    <b>NetEventQueryPower</b> or a 
    <b>NetEventQueryRemoveDevice</b>, the intermediate driver must check the NDIS_STATUS value that is
    returned by 
    <b>NdisMNetPnPEvent</b>. If the returned status is NDIS_STATUS_SUCCESS, the intermediate driver should
    handle the event and then return NDIS_STATUS_SUCCESS from its 
    <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function. If the returned status is not NDIS_STATUS_SUCCESS, the intermediate
    driver should return the reported status from its 
    <i>ProtocolNetPnPEvent</i> function without further processing.

How the intermediate driver processes a 
    <b>NetEventSetPower</b> received by its 
    <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function depends on the specified device power state. If the specified device
    power state is 
    <b>NdisDeviceStateD0</b>, the intermediate driver should handle the event and then call 
    <b>NdisMNetPnPEvent</b>. For any other specified device power state, the intermediate driver should first
    call 
    <b>NdisMNetPnPEvent</b> and then handle the event.

An intermediate driver should call 
    <b>NdisMNetPnPEvent</b> to propagate a 
    <b>NetEventReconfigure</b> or 
    <b>NetEventBindList</b> only if the 
    <b>NetEventReconfigure</b> or 
    <b>NetEventBindList</b> is indicated on a non-<b>NULL</b>
<i>ProtocolBindingContext</i>. If a 
    <b>NetEventReconfigure</b> or 
    <b>NetEventBindList</b> is indicated on a <b>NULL</b>
<i>ProtocolBindingContext</i>, the intermediate driver should not call 
    <b>NdisMNetPnPEvent</b> to propagate the event.

If an intermediate driver handles a 
    <b>NetEventReconfigure</b> or a 
    <b>NetEventBindList</b>, it should validate any data associated with the event.

An intermediate driver should not propagate the 
    <b>NetEventBindsComplete</b>, 
    <b>NetEventPause</b>, 
    <b>NetEventRestart</b>, 
    <b>NetEventPortActivation</b>, or 
    <b>NetEventPortDeactivation</b> events by calling 
    <b>NdisMNetPnPEvent</b>.

An NDIS intermediate driver can generate its own NDIS port events for virtual miniports as
    appropriate for the 
    <b>NetEventPortActivation</b> or 
    <b>NetEventPortDeactivation</b> events that it receives at its 
    <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function.

For all other propagated events, the intermediate driver's 
    <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function should propagate the status value that is returned by 
    <b>NdisMNetPnPEvent</b>.




## -see-also

<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>



<a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\ns-ndis-_net_pnp_event_notification.md">NET_PNP_EVENT_NOTIFICATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMNetPnPEvent function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

