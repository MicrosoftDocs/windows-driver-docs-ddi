---
UID: NC:ndis.NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS
title: NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS (ndis.h)
description: The GetNetBufferListDestinations function returns the Hyper-V extensible switch destination ports of a packet that is specified by a NET_BUFFER_LIST structure.
old-location: netvista\GetNetBufferListDestinations.htm
tech.root: netvista
ms.assetid: 55B5C0B4-5359-410B-9110-79EDDBA3010C
ms.date: 05/02/2018
ms.keywords: GetNetBufferListDestinations, GetNetBufferListDestinations callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS, NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS callback, ndis/GetNetBufferListDestinations, netvista.GetNetBufferListDestinations
ms.topic: callback
f1_keywords:
 - "ndis/GetNetBufferListDestinations"
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
- GetNetBufferListDestinations
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS callback function


## -description



The <i>GetNetBufferListDestinations</i> function returns the Hyper-V extensible switch destination ports of a packet that is specified by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.




## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList [in, out]

A pointer to a linked list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures.  

<div class="alert"><b>Note</b>  If the <i>NetBufferList</i> parameter contains a pointer to a linked-list of multiple <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures, the destination ports are only returned from the first  <b>NET_BUFFER_LIST</b> structure in the list.</div>
<div> </div>

### -param Destinations [out]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. This structure specifies the extensible switch destination ports of the packet.


## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension calls the <i>GetNetBufferListDestinations</i> function to obtain an array of the extensible switch destination ports for a packet. If the function returns successfully, the array is obtained through the <i>Destinations</i> parameter, which contains a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. Each element in this array is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> structure that specifies a destination port for the packet.

If the extension is allocating a packet, the extension must first call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a> function before it calls <i>GetNetBufferListDestinations</i>. The <i>AllocateNetBufferListForwardingContext</i> function allocates the extensible switch forwarding context for the packet. This context contains the out-of-band (OOB) extensible switch data that includes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. 

For more information about the extensible switch forwarding context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-forwarding-context">Hyper-V Extensible Switch Forwarding Context</a>.

After the extension has obtained the array, it can do the following:

<ul>
<li>
Allocate space for additional <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> elements in the array. 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/adding-extensible-switch-destination-port-data-to-a-packet">Adding Extensible Switch Destination Port Data to a Packet</a>.

</li>
<li>
Modify the destination port information in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> elements of the array. For example, the extension can specify which port the packet is to be forwarded to or can exclude a packet from being forwarded to a specified port.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/modifying-a-packet-s-extensible-switch-source-port-data">Modifying a Packet's Extensible Switch Source Port Data</a>.

</li>
</ul>
<div class="alert"><b>Note</b>  The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure is guaranteed to be valid while the extension retains ownership of the packet's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.</div>
<div> </div>



## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>
 

 

