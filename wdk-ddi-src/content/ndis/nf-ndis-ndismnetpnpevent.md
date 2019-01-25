---
UID: NF:ndis.NdisMNetPnPEvent
title: NdisMNetPnPEvent function (ndis.h)
description: NDIS miniport drivers (and intermediate drivers that are registered as miniport drivers) call the NdisMNetPnPEvent function to originate a network Plug and Play event, an NDIS PnP event, or Power Management event or propagate it to overlying drivers.
old-location: netvista\ndismnetpnpevent.htm
tech.root: netvista
ms.assetid: cbb097c1-dd20-4c6d-b23a-1e7683ac3e94
ms.date: 05/02/2018
ms.keywords: NdisMNetPnPEvent, NdisMNetPnPEvent function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_0f39567c-b58c-438e-936e-36323bbc2ea6.xml, ndis/NdisMNetPnPEvent, netvista.ndismnetpnpevent
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMNetPnPEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMNetPnPEvent function


## -description


NDIS miniport drivers (and intermediate drivers that are registered as miniport drivers) call the 
  <b>NdisMNetPnPEvent</b> function to originate a network Plug and Play event, an NDIS PnP event,
  or Power Management event or propagate it to overlying drivers.


## -parameters




### -param MiniportAdapterHandle [in]

An NDIS handle which NDIS provided at the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function.
     This handle identifies the miniport adapter that is affected by the event. If the caller is an
     intermediate driver, this is the handle of the virtual miniport.


### -param NetPnPEventNotification

A pointer to a 
     <a href="https://msdn.microsoft.com/58d3baf3-a1fa-42ae-b795-2774a148aeda">
     NET_PNP_EVENT_NOTIFICATION</a> structure, which describes the network Plug and Play event, NDIS PnP
     event, or Power Management event.

> [!IMPORTANT]
> If the **VPortId** field of **NetPnpEventNotification** is set to a value different from NDIS_DEFAULT_VPORT_ID, then the **Flags** member must be set to NET_EVENT_FLAGS_VPORT_ID_VALID for **VPortId** to take effect.

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
<li>Its <a href="https://msdn.microsoft.com/733d84f5-c1d4-42a0-a59b-4ba50247f165">MiniportOidRequest</a> function must not call 
    <b>NdisMNetPnPEvent</b>.</li>
<li> If its <a href="https://msdn.microsoft.com/733d84f5-c1d4-42a0-a59b-4ba50247f165">MiniportOidRequest</a> function returns NDIS_STATUS_PENDING for an OID request, the NDIS driver must not call 
    <b>NdisMNetPnPEvent</b> until after it has completed the OID request by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff563622">NdisMOidRequestComplete</a>.</li>
</ul>
</div>
<div> </div>
To propagate notification of a network Plug and Play event, an NDIS PnP event, or Power Management
    event to overlying drivers, an NDIS intermediate driver calls 
    <b>NdisMNetPnPEvent</b> in the context of the driver's 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function.

If the propagated event is a 
    <b>NetEventQueryPower</b> or a 
    <b>NetEventQueryRemoveDevice</b>, the intermediate driver must check the NDIS_STATUS value that is
    returned by 
    <b>NdisMNetPnPEvent</b>. If the returned status is NDIS_STATUS_SUCCESS, the intermediate driver should
    handle the event and then return NDIS_STATUS_SUCCESS from its 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function. If the returned status is not NDIS_STATUS_SUCCESS, the intermediate
    driver should return the reported status from its 
    <i>ProtocolNetPnPEvent</i> function without further processing.

How the intermediate driver processes a 
    <b>NetEventSetPower</b> received by its 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function depends on the specified device power state. If the specified device
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
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function.

For all other propagated events, the intermediate driver's 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function should propagate the status value that is returned by 
    <b>NdisMNetPnPEvent</b>.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/733d84f5-c1d4-42a0-a59b-4ba50247f165">MiniportOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568752">NET_PNP_EVENT_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a>
 

 

