---
UID: NS:ndischimney._NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
title: _NDIS_MINIPORT_OFFLOAD_BLOCK_LIST (ndischimney.h)
description: The NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure is the basic building block of a TCP chimney offload state tree. An offload state tree can contain one or more NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures.
old-location: netvista\ndis_miniport_offload_block_list.htm
tech.root: netvista
ms.assetid: ebc98e65-5d11-4c3d-aea1-dfad1434c093
ms.date: 05/02/2018
ms.keywords: "*PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST, NDIS_MINIPORT_OFFLOAD_BLOCK_LIST, NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST, PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_OFFLOAD_BLOCK_LIST, ndischimney/NDIS_MINIPORT_OFFLOAD_BLOCK_LIST, ndischimney/PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST, netvista.ndis_miniport_offload_block_list, tcp_chim_struct_34a99dea-527f-421e-a3a7-92a7c1f7d503.xml"
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- ndischimney.h
api_name:
- NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_OFFLOAD_BLOCK_LIST, *PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST
---

# _NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure is the basic building block of a TCP chimney offload
  state tree. An offload state tree can contain one or more NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
  structures.


## -struct-fields




### -field Header

The header of the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure. The header is formatted as an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
     structure, the type of offload state that immediately follows the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
     structure in memory, and the size of the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure, including the
     header, in bytes. 
     

The 
     <b>Type</b> member of the NDIS_OBJECT_HEADER structure indicates the type of offload state, and by
     implication, the specific offload state structure (or structures) that immediately follow the
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in memory.

The following OFFLOAD_STATE_TYPE values are supported:





#### NeighborOffloadConstState

Specifies the constant neighbor state. This state is formatted as a 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_neighbor_offload_state_const">
       NEIGHBOR_OFFLOAD_STATE_CONST</a> structure.



#### NeighborOffloadCachedState

Specifies the cached neighbor state. This state is formatted as a 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_neighbor_offload_state_cached">
       NEIGHBOR_OFFLOAD_STATE_CACHED</a> structure.



#### NeighborOffloadDelegatedState

Specifies the delegated neighbor state. This state is formatted as a 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_neighbor_offload_state_delegated">
       NEIGHBOR_OFFLOAD_STATE_DELEGATED</a> structure.



#### NeighborOffloadState

Specifies all of the neighbor state information, including the constant, cached, and delegated
       neighbor state. This state is formatted as a NEIGHBOR_OFFLOAD_STATE_CONST structure, followed by a
       NEIGHBOR_OFFLOAD_STATE_CACHED structure, followed by a NEIGHBOR_OFFLOAD_STATE_DELEGATED
       structure.



#### Ip4OffloadConstState

Specifies the constant path state (IPv4). This state is formatted as a 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_path_offload_state_const">
       PATH_OFFLOAD_STATE_CONST</a> structure.



#### Ip4OffloadCachedState

Specifies the cached path state (IPv4). This state is formatted as a 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_path_offload_state_cached">
       PATH_OFFLOAD_STATE_CACHED</a> structure.



#### Ip4OffloadDelegatedState

Specifies the delegated path state (IPv4). This state is formatted as a 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_path_offload_state_delegated">
       PATH_OFFLOAD_STATE_DELEGATED</a> structure. Currently there is no delegated path state. The
       PATH_OFFLOAD_STATE_DELEGATED structure does not contain any variables.



#### Ip4OffloadState

Specifies all of the path state (IPv4), including the constant, cached, and delegated path
       state. This state is formatted as a PATH_OFFLOAD_STATE_CONST structure, followed by a
       PATH_OFFLOAD_STATE_CACHED structure, followed by a PATH_OFFLOAD_STATE_DELEGATED structure.



#### Ip6OffloadConstState

Specifies the constant path state (IPv6). This state is formatted as a PATH_OFFLOAD_STATE_CONST
       structure.



#### Ip6OffloadCachedState

Specifies the cached path state (IPv6). This state is formatted as a PATH_OFFLOAD_STATE_CACHED
       structure.



#### Ip6OffloadDelegatedState

Specifies the delegated path state (IPv6). This state is formatted as a
       PATH_OFFLOAD_STATE_DELEGATED structure. Currently, there is no delegated path state. The
       PATH_OFFLOAD_STATE_DELEGATED structure does not contain any variables.



#### Ip6OffloadState

Specifies all of the path state information(IPv6), including the constant, cached, and delegated
       path state. This state is formatted as a PATH_OFFLOAD_STATE_CONST structure, followed by a
       PATH_OFFLOAD_STATE_CACHED structure, followed by a PATH_OFFLOAD_STATE_DELEGATED structure.



#### TcpOffloadConstState

Specifies the constant TCP state. This state is formatted as a 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_tcp_offload_state_const">
       TCP_OFFLOAD_STATE_CONST</a> structure.



#### TcpOffloadCachedState

Specifies the cached TCP state. This state is formatted as a 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_tcp_offload_state_cached">
       TCP_OFFLOAD_STATE_CACHED</a> structure.



#### TcpOffloadDelegatedState

Specifies the delegated TCP state. This state is formatted as a 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_tcp_offload_state_delegated">
       TCP_OFFLOAD_STATE_DELEGATED</a> structure.



#### TcpOffloadResourceState

Reserved. This OFFLOAD_STATE_TYPE value, as well as the TCP_OFFLOAD_RESOURCE_STATE structure,
       are currently not used.



#### TcpOffloadState

Specifies all of the TCP state information, including the constant, cached, and delegated TCP
       state. This state is formatted as a TCP_OFFLOAD_STATE_CONST structure, followed by a
       TCP_OFFLOAD_STATE_CACHED structure, followed by a TCP_OFFLOAD_STATE_DELEGATED structure.



#### FilterReservedOffloadState

Reserved for filter drivers.


### -field NextBlock

A pointer to the next NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure at the offload state layer
     (neighbor, path, or TCP) indicated by the 
     <b>Type</b> member of the 
     <b>Header</b> member. NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures that are linked through 
     <b>NextBlock</b> pointers are always at the same layer of the offload state. A 
     <b>NextBlock</b> value of <b>NULL</b> indicates that there is no additional next
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure at this level.


### -field DependentBlockList

A pointer to an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that is at a dependent layer of the
     offload state (a higher layer in the offload state tree). For TCP chimney offload: 
     

<ul>
<li>
The 
       <b>DependentBlockList</b> member of an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure at the neighbor layer
       can point only to an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure at the path layer.

</li>
<li>
The 
       <b>DependentBlockList</b> member of an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure at the path layer can
       point only to an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure at the TCP layer.

</li>
<li>
The 
       <b>DependentBlockList</b> member of an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure at the TCP layer is
       always <b>NULL</b>.

</li>
</ul>
A 
     <b>DependentBlockList</b> value of <b>NULL</b> indicates that there is no dependent
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure.


### -field _NDIS_MINIPORT_OFFLOAD_BLOCK_LIST

 


### -field Status

The completion status of an initiate offload, query offload, update offload, invalidate offload,
     or terminate offload operation that the offload target performed on the state associated with, or
     referenced by, the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure. Depending on the operation, the offload
     target writes one of the following NDIS_STATUS values to the 
     <b>Status</b> member:
     





#### NDIS_STATUS_SUCCESS

Initiate offload: The offload target successfully offloaded the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure and the state associated with all of the immediately
       dependent NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures.
       

Query, update, invalidate, or terminate offload: The offload target successfully performed the
       operation on the state associated with, or referenced by, the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
       structure.



#### NDIS_STATUS_OFFLOAD_PARTIAL_SUCCESS

Initiate offload: The offload target successfully offloaded the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure, but failed to offload the state associated with one or
       more of the immediately dependent NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_FAILURE

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure. The cause of the failure cannot be categorized.
       

Query, update, invalidate, or terminate offload: The offload target failed to perform the operation
       on the state associated with, or referenced by, the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
       structure.



#### NDIS_STATUS_RESOURCES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate sufficient
       host memory.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_TCP_ENTRIES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate a TCP
       connection state object.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_PATH_ENTRIES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate a path state
       object.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_NEIGHBOR_ENTRIES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate a neighbor
       state object.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_HW_ADDRESS_ENTRIES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure because the host stack specified a non-<b>NULL</b><b>DlSourceAddress</b> member in the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_neighbor_offload_state_const">
       NEIGHBOR_OFFLOAD_STATE_CONST</a> structure, and the offload target either does not support
       configurable source MAC addresses or cannot accept additional source MAC addresses.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_IP_ADDRESS_ENTRIES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate a data
       structure for the source IP address that is referenced by the 
       <b>SourceAddress</b> pointer in the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_path_offload_state_const">
       PATH_OFFLOAD_STATE_CONST</a> structure.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_TCP_XMIT_BUFFER

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate enough TCP
       transmit buffers.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_TCP_RCV_BUFFER

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate enough TCP
       receive buffers.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_TCP_RCV_WINDOW

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure because the 
       <b>InitialRcvWnd</b> member specified in the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_tcp_offload_state_cached">
       TCP_OFFLOAD_STATE_CACHED</a> structure is larger than the offload target can support.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_VLAN_ENTRIES

Initiate offload: The offload target has run out of resources for tracking additional VLAN IDs. 
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_VLAN_MISMATCH

Initiate offload: The neighbor 
       <b>VlanId</b> is non-zero and does not match one of the interface VLAN IDs.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_PATH_MTU

The path MTU for the TCP connection is larger than the offload target supports.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.


### -field NdisReserved

Reserved for use by NDIS.


### -field MiniportOffloadContext

A pointer to a memory location into which the offload target writes a PVOID value. The PVOID value
     references the offload context area in which the offload target stores the state associated with the
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure. If the state is a new state to be offloaded by the offload
     target, the memory location pointed to by 
     <b>MiniportOffloadContext</b> contains a <b>NULL</b> value. After offloading the state, the offload target
     writes a PVOID value to this memory location. The PVOID value supplied by the offload target references
     the offload context area into which the state was offloaded. If the 
     <b>MiniportOffloadContext</b> member itself is <b>NULL</b>, the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure is a
     placeholder in the offload state tree.


### -field NdisOffloadHandle

The handle that the offload target supplies in subsequent calls to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-ndis_tcp_offload_event_indicate">
     NdisTcpOffloadEventHandler</a> function or the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_indicate">
     NdisTcpOffloadReceiveHandler</a> function when making an indication on the offload state associated
     with this NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure.


### -field ProtocolReserved

Reserved for use by protocol drivers, which can use this area for their own purposes. Offload
     targets must not modify this value.


### -field MiniportReserved

Reserved for use by offload targets, which can use this area for their own purposes, such as
     queuing up the offload state associated with the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure.


### -field ImReserved

Reserved for use by intermediate drivers, which can use this area for their own purposes. Offload
     targets must not modify this value.


### -field Scratch

The offload target can use this area for internal tracking. The information in this area is valid
     only while the offload target has ownership of the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST.


### -field SourceHandle

This member is not significant for an offload target. An offload target must not modify this
     member.


### -field PortNumber

A port number that identifies a miniport adapter port. To assign a miniport adapter port number,
     call the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocateport">NdisMAllocatePort</a> function. A zero
     value identifies the default port of a miniport adapter. Use the default port if the miniport driver has
     not allocated ports for the specified adapter.


### -field NetBufferListChain

When the host stack specifies a <b>NULL</b> value, 
     <b>NetBufferListChain</b> is not significant and can be ignored by the offload target. 
     

When the host stack specifies a non-<b>NULL</b> value, 
     <b>NetBufferListChain</b> points to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that can be a
     stand-alone structure or the first structure in a linked list of such structures. Each NET_BUFFER_LIST
     structure in the linked list describes one 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure. The NET_BUFFER structure
     maps to a chain of memory descriptor lists (MDLs). The NET_BUFFER_LIST and associated structures are
     locked so that they remain resident in physical memory. However, they are not mapped into system
     memory.

The MDLs associated with the NET_BUFFER structures contain data that the host stack is passing to the
     offload target as part of the offload operation. The offload target completes such data asynchronously
     back to the host stack by calling the appropriate 
     <b>NdisTcpOffload<i>Xxx</i>Complete</b> function. At present, the linked list can contain just one type of data:
     outstanding send data. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/handling-outstanding-send-data-during-and-after-an-offload-operation">Handling Outstanding Send Data During and After an Offload Operation</a>.

An offload target can pass outstanding send data to the host stack when terminating the offload of a
     TCP connection. In this case, the offload target specifies a non-<b>NULL</b> value for the 
     <b>NetBufferListChain</b> member when calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndismterminateoffloadcomplete">
     NdisMTerminateOffloadComplete</a> function. If the offload target is not passing send data for a TCP
     connection that is being terminated, it must specify a <b>NULL</b> value for the 
     <b>NetBufferListChain</b> member.


## -remarks



NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures can be linked together to build the framework of a TCP
    chimney 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/offload-state-tree">offload state tree</a>.

Through NDIS, the host stack passes an 
    <i>OffloadBlockList</i> pointer, which references an offload state tree to one of the following functions
    of an offload target:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_initiate_offload_handler">MiniportInitiateOffload</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_query_offload_handler">MiniportQueryOffload</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_update_offload_handler">MiniportUpdateOffload</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_invalidate_offload_handler">MiniportInvalidateOffload</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_terminate_offload_handler">MiniportTerminateOffload</a>


</li>
</ul>
The offload target returns the tree to the host stack by passing the same pointer to the corresponding
    completion function:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndisminitiateoffloadcomplete">
       NdisMInitiateOffloadComplete</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndismqueryoffloadstatecomplete">
       NdisMQueryOffloadStateComplete</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndismupdateoffloadcomplete">NdisMUpdateOffloadComplete</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndisminvalidateoffloadcomplete">
       NdisMInvalidateOffloadComplete</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndismterminateoffloadcomplete">
       NdisMTerminateOffloadComplete</a>


</li>
</ul>
An NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure can be immediately followed in memory by an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_tcp_offload_state_delegated">offload state structure</a> that contains
    state to be offloaded, queried, updated, invalidated, or terminated. The 
    <b>Type</b> member of the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure's 
    <b>Header</b> specifies the type of offload state, and by implication, the specific offload state
    structure (or structures) that follow the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in memory.

The host stack and offload target use the 
    <b>*MiniportOffloadContext</b> and 
    <b>NdisOffloadHandle</b> members of an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure to reference offloaded
    state. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/storing-and-referencing-offloaded-state">Storing and Referencing
    Offloaded State</a>.

An NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure can perform one of several functions in an offload state
    tree. It can function as a placeholder, a linker, or it can convey new state to be offloaded by the
    offload target. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/placeholders--linkers--and-new-offloads">Placeholders, Linkers, and
    New Offloads</a>.

Before completing an initiate offload, query offload, update offload, invalidate offload, or terminate
    offload operation, an offload target must write the completion status to the 
    <b>Status</b> member of each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_initiate_offload_handler">MiniportInitiateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_invalidate_offload_handler">MiniportInvalidateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_query_offload_handler">MiniportQueryOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_terminate_offload_handler">MiniportTerminateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_update_offload_handler">MiniportUpdateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_neighbor_offload_state_cached">NEIGHBOR_OFFLOAD_STATE_CACHED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_neighbor_offload_state_delegated">
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocateport">NdisMAllocatePort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndisminitiateoffloadcomplete">NdisMInitiateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndisminvalidateoffloadcomplete">
   NdisMInvalidateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndismqueryoffloadstatecomplete">
   NdisMQueryOffloadStateComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndismterminateoffloadcomplete">
   NdisMTerminateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndismupdateoffloadcomplete">NdisMUpdateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-ndis_tcp_offload_event_indicate">NdisTcpOffloadEventHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_indicate">NdisTcpOffloadReceiveHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_path_offload_state_cached">PATH_OFFLOAD_STATE_CACHED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_path_offload_state_const">PATH_OFFLOAD_STATE_CONST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_path_offload_state_delegated">PATH_OFFLOAD_STATE_DELEGATED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_tcp_offload_state_cached">TCP_OFFLOAD_STATE_CACHED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_tcp_offload_state_const">TCP_OFFLOAD_STATE_CONST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_tcp_offload_state_delegated">TCP_OFFLOAD_STATE_DELEGATED</a>
 

 

