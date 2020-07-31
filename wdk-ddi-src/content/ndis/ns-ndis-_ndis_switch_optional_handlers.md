---
UID: NS:ndis._NDIS_SWITCH_OPTIONAL_HANDLERS
title: _NDIS_SWITCH_OPTIONAL_HANDLERS (ndis.h)
description: The NDIS_SWITCH_OPTIONAL_HANDLERS structure specifies the pointers to the Hyper-V extensible switch handler functions. These functions can be called by an extensible switch extension.
old-location: netvista\ndis_switch_optional_handlers.htm
tech.root: netvista
ms.assetid: aa8367c7-8366-4601-8c2a-4d96df5cfcd8
ms.date: 05/02/2018
keywords: ["_NDIS_SWITCH_OPTIONAL_HANDLERS structure"]
ms.keywords: "*PNDIS_SWITCH_OPTIONAL_HANDLERS, NDIS_SWITCH_OPTIONAL_HANDLERS, NDIS_SWITCH_OPTIONAL_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_OPTIONAL_HANDLERS, PNDIS_SWITCH_OPTIONAL_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_OPTIONAL_HANDLERS, ndis/NDIS_SWITCH_OPTIONAL_HANDLERS, ndis/PNDIS_SWITCH_OPTIONAL_HANDLERS, netvista.ndis_switch_optional_handlers"
f1_keywords:
 - "ndis/NDIS_SWITCH_OPTIONAL_HANDLERS"
 - "NDIS_SWITCH_OPTIONAL_HANDLERS"
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
- NDIS_SWITCH_OPTIONAL_HANDLERS
targetos: Windows
req.typenames: NDIS_SWITCH_OPTIONAL_HANDLERS, *PNDIS_SWITCH_OPTIONAL_HANDLERS
---

# _NDIS_SWITCH_OPTIONAL_HANDLERS structure


## -description


The <b>NDIS_SWITCH_OPTIONAL_HANDLERS</b> structure specifies the pointers to the Hyper-V extensible switch handler functions. These functions can be called by an extensible switch extension.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_OPTIONAL_HANDLERS</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_OPTIONAL_HANDLERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_OPTIONAL_HANDLERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_NIC_ARRAY_REVISION_1.


### -field AllocateNetBufferListForwardingContext

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a> function.


### -field FreeNetBufferListForwardingContext

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_free_net_buffer_list_forwarding_context">FreeNetBufferListForwardingContext</a> function.


### -field SetNetBufferListSource

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_set_net_buffer_list_source">SetNetBufferListSource</a> function.


### -field AddNetBufferListDestination

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_add_net_buffer_list_destination">AddNetBufferListDestination</a> function.


### -field GrowNetBufferListDestinations

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_grow_net_buffer_list_destinations">GrowNetBufferListDestinations</a> function.


### -field GetNetBufferListDestinations

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_get_net_buffer_list_destinations">GetNetBufferListDestinations</a> function.


### -field UpdateNetBufferListDestinations

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_update_net_buffer_list_destinations">UpdateNetBufferListDestinations</a> function.


### -field CopyNetBufferListInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_copy_net_buffer_list_info">CopyNetBufferListInfo</a> function.


### -field ReferenceSwitchNic

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_nic">ReferenceSwitchNic</a> function.


### -field DereferenceSwitchNic

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_dereference_switch_nic">DereferenceSwitchNic</a> function.


### -field ReferenceSwitchPort

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_port">ReferenceSwitchPort</a> function.


### -field DereferenceSwitchPort

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_dereference_switch_port">DereferenceSwitchPort</a> function.


### -field ReportFilteredNetBufferLists

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_report_filtered_net_buffer_lists">ReportFilteredNetBufferLists</a> function.


### -field SetNetBufferListSwitchContext

 


### -field GetNetBufferListSwitchContext

 


### -field SwitchPDReserved

 




## -remarks



The extensible switch handler functions provide support for filtering and forwarding actions that are performed by an extensible switch extension. These actions include the following:


<ul>
<li>
Allocate or free  the forwarding context. This data is stored in the out-of-band (OOB) data of a packet's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. For more information about the forwarding context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-forwarding-context">Hyper-V Extensible Switch Forwarding Context</a>.

</li>
<li>
Get or set the destination ports that are contained in a packet's forwarding context.

</li>
<li>
Add destination ports to a packet's forwarding context.

</li>
</ul>


When the extensible switch extension calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>, the <i>NdisSwitchHandlers</i> parameter contains a pointer to an  <b>NDIS_SWITCH_OPTIONAL_HANDLERS</b> structure. An extensible switch extension typically calls <b>NdisFGetOptionalSwitchHandlers</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_add_net_buffer_list_destination">AddNetBufferListDestination</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_copy_net_buffer_list_info">CopyNetBufferListInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_dereference_switch_nic">DereferenceSwitchNic</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_dereference_switch_port">DereferenceSwitchPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_free_net_buffer_list_forwarding_context">FreeNetBufferListForwardingContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_grow_net_buffer_list_destinations">GrowNetBufferListDestinations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_nic">ReferenceSwitchNic</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_port">ReferenceSwitchPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_report_filtered_net_buffer_lists">ReportFilteredNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_set_net_buffer_list_source">SetNetBufferListSource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_update_net_buffer_list_destinations">UpdateNetBufferListDestinations</a>
 

 

