---
UID: NC:ndis.NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION
title: NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION (ndis.h)
description: The AddNetBufferListDestination function adds a single destination port for a packet that is specified by a NET_BUFFER_LIST structure.
old-location: netvista\AddNetBufferListDestination.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION callback function"]
ms.keywords: AddNetBufferListDestination, AddNetBufferListDestination callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION, NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION callback, ndis/AddNetBufferListDestination, netvista.AddNetBufferListDestination
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION
 - ndis/NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - AddNetBufferListDestination
---

# NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION callback function


## -description

The <i>AddNetBufferListDestination</i> function adds a single destination port for a packet that is specified by a <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

## -parameters

### -param NdisSwitchContext 

[in]
An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.

### -param NetBufferList 

[in, out]
A pointer to a <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure for a packet. 

<div class="alert"><b>Note</b>  This structure must contain  an extensible switch forwarding context. If the extension created or cloned the  packet, it must have previously allocated this structure by calling the <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a> function.</div>
<div> </div>

### -param Destination 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> structure. This structure specifies the destination extensible switch port that the packet will be forwarded to.

## -returns

If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.

## -remarks

The forwarding extensible switch extension calls <i>AddNetBufferListDestination</i> to define a single extensible switch destination port for a packet. The extension specifies this port by initializing an   <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> structure. The extension sets the <i>Destination</i> parameter to a pointer to this structure. For more information on how to specify an extensible switch destination port, see <a href="/windows-hardware/drivers/network/managing-hyper-v-extensible-switch-destination-port-data">Managing Hyper-V Extensible Switch Destination Port Data</a>.

<div class="alert"><b>Note</b>  For performance reasons, the extension should not call <i>AddNetBufferListDestination</i> packets with multiple destination ports.</div>
<div> </div>
The extension must follow these guidelines before it calls <i>AddNetBufferListDestination</i>:

<ul>
<li>
Only forwarding extensions can call <i>AddNetBufferListDestination</i> to add a destination port for a packet. For more information on this type of extension, see <a href="/windows-hardware/drivers/network/forwarding-extensions">Forwarding Extensions</a>.

</li>
<li>
If the forwarding extension is originating a packet with one destination port, the extension must first call the <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a> function. This function allocates the extensible switch forwarding context for the packet. This data contains the extensible switch source and destination ports within the out-of-band (OOB) information for the packet.

For more information about this context, see <a href="/windows-hardware/drivers/network/hyper-v-extensible-switch-forwarding-context">Hyper-V Extensible Switch Forwarding Context</a>.

</li>
<li>
After the extension modifies the destination port information in the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> structure, it calls <i>AddNetBufferListDestination</i> to commit the changes to the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure for the packet.

<div class="alert"><b>Note</b>  For performance reasons, the extension should not call the <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_update_net_buffer_list_destinations">UpdateNetBufferListDestinations</a> function to commit the changes for the packet.
</div>
<div> </div>
</li>
</ul>
<div class="alert"><b>Note</b>  After the forwarding extension commits the changes for destination ports to the forwarding context, destination ports cannot be removed and only the <b>IsExcluded</b>  member of a destination port's <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> structure can be changed. For more information, see <a href="/windows-hardware/drivers/network/excluding-packet-delivery-to-extensible-switch-destination-ports">Excluding Packet Delivery to Extensible Switch Destination Ports</a>.</div>
<div> </div>

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_get_net_buffer_list_destinations">GetNetBufferListDestinations</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_update_net_buffer_list_destinations">UpdateNetBufferListDestinations</a>
