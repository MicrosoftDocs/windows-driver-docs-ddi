---
UID: NC:ndis.NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT
title: NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT (ndis.h)
description: The AllocateNetBufferListForwardingContext function prepares a NET_BUFFER_LIST structure for send or receive operations within the extensible switch.
old-location: netvista\AllocateNetBufferListForwardingContext.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback function"]
ms.keywords: AllocateNetBufferListForwardingContext, AllocateNetBufferListForwardingContext callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT, NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback, ndis/AllocateNetBufferListForwardingContext, netvista.AllocateNetBufferListForwardingContext
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
 - NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT
 - ndis/NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT
---

# NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback function


## -description

The <i>AllocateNetBufferListForwardingContext</i> function prepares a <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure for send or receive operations within the extensible switch.

## -parameters

### -param NdisSwitchContext 

[in]
An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.

### -param NetBufferList 

[in, out]
A pointer to a linked list of <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures.

## -returns

If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.

## -remarks

The extensible switch extension can originate packet send operations within the extensible switch data path. For example, the extension can send packets to any port on the extensible switch. For more information about this data path, see <a href="/windows-hardware/drivers/network/hyper-v-extensible-switch-data-path">Hyper-V Extensible Switch Data Path</a>.

After the extension calls <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a> or <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">NdisAllocateCloneNetBufferList</a> to create or clone a packet from its <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> pool, the extension must  call the <i>AllocateNetBufferListForwardingContext</i> function. This function allocates and initializes the out-of-band (OOB) extensible switch forwarding context for the specified  <b>NET_BUFFER_LIST</b> structure. For more information about this context, see <a href="/windows-hardware/drivers/network/hyper-v-extensible-switch-forwarding-context">Hyper-V Extensible Switch Forwarding Context</a>.

The extension must follow these guidelines for allocating the forwarding context through the <i>AllocateNetBufferListForwardingContext</i> function:

<ul>
<li>
The extension calls <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a> to allocate a packet from the extension's <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> pool for a send or receive operation over the extensible switch. Before the extension initializes source and destination ports for the packet, it must call <i>AllocateNetBufferListForwardingContext</i>. 

For more information on how to specify source and destination extensible switch ports, see <a href="/windows-hardware/drivers/network/managing-hyper-v-extensible-switch-source-and-destination-port-data">Managing Hyper-V Extensible Switch Source and Destination Port Data</a>.

</li>
<li>
Before the extension calls <i>AllocateNetBufferListForwardingContext</i>, it must set the <b>SourceHandle</b> member of each allocated <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure to the handle value that identifies the extension. The extension receives this handle through the <i>NdisFilterHandle</i> parameter when NDIS calls the extension's <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

</li>
<li>
When the send operation is complete, the extension must call the <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_free_net_buffer_list_forwarding_context">FreeNetBufferListForwardingContext</a> function to deallocate the resources for the forwarding context. The extension must call this function before it calls <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a> to return the packet to its <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> pool.

</li>
<li>
If the extension is cloning a packet, it must call <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_copy_net_buffer_list_info">CopyNetBufferListInfo</a> to copy the forwarding context from the original packet to the cloned packet. The extension must do this after it calls <i>AllocateNetBufferListForwardingContext</i>.

</li>
</ul>
 For more information on how to originate send operations, see <a href="/windows-hardware/drivers/network/filter-module-send-and-receive-operations">Filter Module Send and Receive Operations</a>.

<div class="alert"><b>Note</b>  If the <i>NetBufferList</i> parameter contains a pointer to a linked-list of multiple <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures, only the first  <b>NET_BUFFER_LIST</b> structure in the list has a forwarding context allocated for it.</div>
<div> </div>

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_copy_net_buffer_list_info">CopyNetBufferListInfo</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_free_net_buffer_list_forwarding_context">FreeNetBufferListForwardingContext</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a>

