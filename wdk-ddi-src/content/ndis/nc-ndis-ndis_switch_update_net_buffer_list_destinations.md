---
UID: NC:ndis.NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS
title: NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS (ndis.h)
description: The Hyper-V extensible switch extension calls the UpdateNetBufferListDestinations function to commit modifications that the extension made to a packet that contains multiple extensible switch destination ports.
old-location: netvista\UpdateNetBufferListDestinations.htm
tech.root: netvista
ms.assetid: 9A740524-0FC1-4585-8059-F678D4777F66
ms.date: 05/02/2018
ms.keywords: NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS, NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS callback, UpdateNetBufferListDestinations, UpdateNetBufferListDestinations callback function [Network Drivers Starting with Windows Vista], ndis/UpdateNetBufferListDestinations, netvista.UpdateNetBufferListDestinations
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- UpdateNetBufferListDestinations
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS callback function


## -description



The Hyper-V extensible switch extension calls the <i>UpdateNetBufferListDestinations</i> function to commit modifications that the extension made to a packet that contains multiple extensible switch destination ports. The function saves these modifications to the out-of-band (OOB) extensible switch forwarding context of the packet's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. 




## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure for a single packet.

<div class="alert"><b>Note</b>  This structure must contain  an extensible switch forwarding context. If the extension created or cloned the  packet, it must have previously allocated this structure by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a> function.</div>
<div> </div>

### -param NumberOfNewDestinations [in]

A UINT32 value that specifies the number of new destination ports that were added to the packet.


### -param Destinations [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. This structure specifies the extensible switch destination ports of the packet.

<div class="alert"><b>Note</b>  The extension received this structure through a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_switch_get_net_buffer_list_destinations">GetNetBufferListDestinations</a> function.</div>
<div> </div>

## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_switch_get_net_buffer_list_destinations">GetNetBufferListDestinations</a> function to obtain an array of the extensible switch destination ports for a packet. If the function returns successfully, the array is obtained through the <i>Destinations</i> parameter, which contains a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. Each element in this array is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> structure that specifies a destination port for the packet.

After the extension obtains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure, the extension can do the following:

<ul>
<li>
Add additional <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> elements in the array.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/adding-extensible-switch-destination-port-data-to-a-packet">Adding Extensible Switch Destination Port Data to a Packet</a>.

</li>
<li>
Modify existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> elements of the array to exclude a packet from being forwarded to a specified port.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/excluding-packet-delivery-to-extensible-switch-destination-ports">Excluding Packet Delivery to Extensible Switch Destination Ports</a>.

</li>
</ul>
If the extension adds or modifies destination ports in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure, the extension must call the <i>UpdateNetBufferListDestinations</i> function to commit those changes to the packet's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

<div class="alert"><b>Note</b>  Only forwarding extensions can call <i>UpdateNetBufferListDestinations</i> to commit destination ports that were added or changed for packets with multiple destination ports. For more information on this type of extension, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/forwarding-extensions">Forwarding Extensions</a>.</div>
<div> </div>
If the call to <i>UpdateNetBufferListDestinations</i> returns NDIS_STATUS_SUCCESS, the extensible switch interface guarantees that the extensible switch port and network adapter connection that are referenced in the destination ports will not be deleted until the packet's send or receive operation is completed. 

Also, after the changes for destination ports have been committed, destination ports cannot be removed, and only the <b>IsExcluded</b>  member of a destination port's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> structure can be changed. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/excluding-packet-delivery-to-extensible-switch-destination-ports">Excluding Packet Delivery to Extensible Switch Destination Ports</a>.

<div class="alert"><b>Note</b>  For performance reasons, the extension should not call the <i>UpdateNetBufferListDestinations</i> function to commit the changes to a packet with only one destination port.
Instead, the extension calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_switch_add_net_buffer_list_destination">AddNetBufferListDestination</a> to commit the changes to the packet's destination port.</div>
<div> </div>
For more information about the extensible switch forwarding context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-forwarding-context">Hyper-V Extensible Switch Forwarding Context</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_switch_get_net_buffer_list_destinations">GetNetBufferListDestinations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfoidrequest">NdisFOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-delete">OID_SWITCH_NIC_DELETE</a>
 

 

