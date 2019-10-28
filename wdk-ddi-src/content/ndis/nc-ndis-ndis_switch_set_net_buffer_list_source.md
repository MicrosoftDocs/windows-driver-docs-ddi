---
UID: NC:ndis.NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE
title: NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE (ndis.h)
description: The SetNetBufferListSource function sets the Hyper-V extensible switch source port identifier and network adapter index for a packet that is specified by a NET_BUFFER_LIST structure.
old-location: netvista\setnetbufferlistsource.htm
tech.root: netvista
ms.assetid: 6537824A-F521-4916-AAC8-7C0E6E5F7331
ms.date: 05/02/2018
ms.keywords: NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE, NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE callback, SetNetBufferListSource, SetNetBufferListSource callback function [Network Drivers Starting with Windows Vista], ndis/SetNetBufferListSource, netvista.setnetbufferlistsource
ms.topic: callback
f1_keywords:
 - "ndis/SetNetBufferListSource"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- SetNetBufferListSource
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE callback function


## -description



The <i>SetNetBufferListSource</i> function sets the Hyper-V extensible switch source port identifier and network adapter index for a packet that is specified by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.




## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure for a single packet.  

<div class="alert"><b>Note</b>  This structure must contain  an extensible switch forwarding context that was previously allocated by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a> function. For more information about the extensible switch forwarding context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-forwarding-context">Hyper-V Extensible Switch Forwarding Context</a>.</div>
<div> </div>

### -param PortId [in]

An NDIS_SWITCH_PORT_ID value that specifies the unique identifier of the source port on the extensible switch.


### -param NicIndex [in]

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the network adapter that is connected to the extensible switch port specified by the <i>PortId</i> parameter.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-adapter-index-values">Network Adapter Index Values</a>.



<div class="alert"><b>Note</b>  This parameter must specify the index value of a network adapter that is in a connected state. Index values for network adapters that are in a created or disconnected state cannot be specified. For more information about network connection states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-port-and-network-adapter-states">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div>
<div> </div>


## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension calls the <i>SetNetBufferListSource</i> function to set the source port identifier and network adapter index in a packet's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. The extension does this for the following types of packets:

<ul>
<li>
A new packet that the extension has allocated for send or receive operations.

<div class="alert"><b>Note</b>  Before the extension calls <i>SetNetBufferListSource</i> for an allocated packet, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a>. </div>
<div> </div>
</li>
<li>
A duplicated packet that the extension had cloned from an original packet that it was filtering. The extension duplicates a packet by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">NdisAllocateCloneNetBufferList</a>.

</li>
</ul>
In both cases, a new or duplicated packet will have its source port identifier set to <b>NDIS_SWITCH_DEFAULT_PORT_ID</b> and its source network adapter index set to <b>NDIS_SWITCH_DEFAULT_NIC_INDEX</b>. The extension  calls the <i>SetNetBufferListSource</i> function to change the source port identifier and network adapter index in a packet's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

For example, a packet that has a source port identifier of <b>NDIS_SWITCH_DEFAULT_PORT_ID</b> is trusted and bypasses many extensible switch port policies. These policies include access control lists (ACLs) and quality of service (QoS). If the extension specifies a non-default source port for the packet, this allows the policies for that port to be applied to the packet.

<div class="alert"><b>Note</b>  Because packets with a source port identifier of <b>NDIS_SWITCH_DEFAULT_PORT_ID</b> are trusted, the extension must use this source port identifier very carefully when it originates packet traffic. For more information on the recommended use of the <b>NDIS_SWITCH_DEFAULT_PORT_ID</b> for source ports, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/managing-hyper-v-extensible-switch-source-port-data">Managing Hyper-V Extensible Switch Source Port Data</a>.</div>
<div> </div>
For more information on packet send and receive operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/filter-module-send-and-receive-operations">Filter Module Send and Receive Operations</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_allocate_net_buffer_list_forwarding_context">AllocateNetBufferListForwardingContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">NdisAllocateCloneNetBufferList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>
 

 

