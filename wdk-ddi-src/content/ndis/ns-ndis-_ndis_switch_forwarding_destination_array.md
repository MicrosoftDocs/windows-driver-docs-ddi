---
UID: NS:ndis._NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
title: _NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY (ndis.h)
description: The NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure specifies an array of Hyper-V extensible switch destination ports for a packet.
old-location: netvista\ndis_switch_forwarding_destination_array.htm
tech.root: netvista
ms.assetid: f48b3b5f-000e-4e57-87b7-52ce542773f7
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, ndis/NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, ndis/PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, netvista.ndis_switch_forwarding_destination_array"
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ndis.h
api_name:
- NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY, *PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY
---

# _NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure


## -description



The <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure specifies an array of Hyper-V extensible switch destination ports for a packet.  Each element in the array is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> structure. 

This information is contained in the out-of-band (OOB) data of the packet's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.




## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY_REVISION_1.


### -field ElementSize

A ULONG value that specifies the size, in bytes, of each <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> element that follows the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure. 


### -field NumElements

A ULONG value that specifies the total number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> elements in the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure. 

The value of the <b>NumElements</b> member specifies the number of currently used <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> elements (as specified by the <b>NumDestinations</b> member) plus the number of elements that are available for new destination ports. The number of unused <b>NDIS_SWITCH_PORT_DESTINATION</b> elements in the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure is calculated by (<b>NumElements</b> - <b>NumDestinations</b>).


### -field NumDestinations

A ULONG value that specifies the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> elements in the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure that specify port destinations. 

<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field FirstElement

A pointer to the first <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> element in the buffer that contains the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure and all its elements.


## -remarks



The extensible switch extension can do the following with the destination ports  in a packet's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure:

<ul>
<li>
Query the current destination ports on the extensible switch that the packet will be forwarded to. 

The extensible switch extension calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_get_net_buffer_list_destinations">GetNetBufferListDestinations</a> function to obtain the array of port destinations for a packet. <i>GetNetBufferListDestinations</i> returns a pointer to the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure in the <i>Destinations</i> parameter.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/querying-a-packet-s-extensible-switch-destination-port-data">Querying a Packet's Extensible Switch Destination Port Data</a>.

</li>
<li>
Add or modify the destination ports for the packet. 

After it queries the current destination ports for the packet, the extensible switch extension can do the following:

<ul>
<li>
A forwarding extension can add new destination ports to the <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> structure.

</li>
<li>
A filtering or forwarding extension can modify the data within an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> structure for a destination port.

<div class="alert"><b>Note</b>  A filtering extension can only change the <b>IsExcluded</b> member of this structure. A forwarding extension can also change the <b>PreserveVLAN</b> and <b>PreservePriority</b> members.</div>
<div> </div>
</li>
</ul>
If the extension adds or modifies port destinations, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_update_net_buffer_list_destinations">UpdateNetBufferListDestinations</a> to commit the changes to the destination ports to the packet's OOB data in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/managing-hyper-v-extensible-switch-destination-port-data">Managing Hyper-V Extensible Switch Destination Port Data</a>.

</li>
</ul>
Extensible switch extensions can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-port-destination-at-array-index">NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX</a> macro to access <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a> elements in an <b>NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</b> array.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/adding-extensible-switch-destination-port-data-to-a-packet">Adding Extensible Switch Destination Port Data to a Packet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/excluding-packet-delivery-to-extensible-switch-destination-ports">Excluding Packet Delivery to Extensible Switch Destination Ports</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/forwarding-extensions">Forwarding Extensions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_get_net_buffer_list_destinations">GetNetBufferListDestinations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/hybrid-forwarding">Hybrid Forwarding</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_port_destination">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-port-destination-at-array-index">NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-the-hyper-v-extensible-switch">Overview of the Hyper-V Extensible Switch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_update_net_buffer_list_destinations">UpdateNetBufferListDestinations</a>
 

 

