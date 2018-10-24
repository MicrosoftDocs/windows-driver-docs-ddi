---
UID: NS:ndischimney._NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST
title: "_NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST"
author: windows-driver-content
description: The NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure.
old-location: netvista\ndis_protocol_offload_block_list.htm
tech.root: netvista
ms.assetid: 64febd55-1ab8-4e2e-b738-340167866333
ms.date: 05/02/2018
ms.keywords: "*PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST, NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST, NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure [Network Drivers Starting with Windows Vista], PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST, PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST, ndischimney/NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST, ndischimney/PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST, netvista.ndis_protocol_offload_block_list, tcp_chim_struct_77380eae-055d-471e-a94a-67575124981b.xml"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndischimney.h
api_name:
-	NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST
product:
- Windows
targetos: Windows
req.typenames: NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST, *PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST
---

# _NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure.


## -struct-fields




### -field Header

The header of the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. The header is formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST
     structure, the type of offload state that immediately follows the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST
     structure in memory, and the size of the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure, including the
     header, in bytes. 
     

The 
     <b>Type</b> member of the NDIS_OBJECT_HEADER structure indicates the type of offload state, and by
     implication, the specific offload state structure (or structures) that immediately follow the
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure in memory.

The following OFFLOAD_STATE_TYPE values are supported:





#### NeighborOffloadConstState

Specifies the constant neighbor state. This state is formatted as a 
       <a href="https://msdn.microsoft.com/1c79a3d6-c365-4740-a2e0-94333b70d8cc">
       NEIGHBOR_OFFLOAD_STATE_CONST</a> structure.



#### NeighborOffloadCachedState

Specifies the cached neighbor state. This state is formatted as a 
       <a href="https://msdn.microsoft.com/5dedffa8-9745-4668-8646-0e896942b9c8">
       NEIGHBOR_OFFLOAD_STATE_CACHED</a> structure.



#### NeighborOffloadDelegatedState

Specifies the delegated neighbor state. This state is formatted as a 
       <a href="https://msdn.microsoft.com/94a35d0f-3585-45d0-bba8-0b4a8ebbe883">
       NEIGHBOR_OFFLOAD_STATE_DELEGATED</a> structure.



#### NeighborOffloadState

Specifies all of the neighbor state, including the constant, cached, and delegated neighbor
       state. This state is formatted as a NEIGHBOR_OFFLOAD_STATE_CONST structure, followed by a
       NEIGHBOR_OFFLOAD_STATE_CACHED structure, followed by a NEIGHBOR_OFFLOAD_STATE_DELEGATED
       structure.



#### Ip4OffloadConstState

Specifies the constant path state (IPv4). This state is formatted as a 
       <a href="https://msdn.microsoft.com/a71f70f6-7731-457b-bd6d-b4a649f76f8b">
       PATH_OFFLOAD_STATE_CONST</a> structure.



#### Ip4OffloadCachedState

Specifies the cached path state (IPv4). This state is formatted as a 
       <a href="https://msdn.microsoft.com/5afd2499-3f47-481e-9d20-770842f79677">
       PATH_OFFLOAD_STATE_CACHED</a> structure.



#### Ip4OffloadDelegatedState

Specifies the delegated path state (IPv4). This state is formatted as a 
       <a href="https://msdn.microsoft.com/3a1603ec-639f-4899-8889-3c7ed2cfe375">
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

Specifies all of the path state (IPv6), including the constant, cached, and delegated path
       state. This state is formatted as a PATH_OFFLOAD_STATE_CONST structure, followed by a
       PATH_OFFLOAD_STATE_CACHED structure, followed by a PATH_OFFLOAD_STATE_DELEGATED structure.



#### TcpOffloadConstState

Specifies the constant TCP state. This state is formatted as a 
       <a href="https://msdn.microsoft.com/3e80f963-a494-475a-a246-abe5674dbcb6">
       TCP_OFFLOAD_STATE_CONST</a> structure.



#### TcpOffloadCachedState

Specifies the cached TCP state. This state is formatted as a 
       <a href="https://msdn.microsoft.com/953154eb-e6f3-4013-a68f-1a358953c7ad">
       TCP_OFFLOAD_STATE_CACHED</a> structure.



#### TcpOffloadDelegatedState

Specifies the delegated TCP state. This state is formatted as a 
       <a href="https://msdn.microsoft.com/ab16cfa1-24f6-434a-a687-07e19172f185">
       TCP_OFFLOAD_STATE_DELEGATED</a> structure.



#### TcpOffloadResourceState

Reserved. This OFFLOAD_STATE_TYPE value, as well as the TCP_OFFLOAD_RESOURCE_STATE structure,
       are currently not used.



#### TcpOffloadState

Specifies all of the TCP state, including the constant, cached, and delegated TCP state. This
       state is formatted as a TCP_OFFLOAD_STATE_CONST structure, followed by a TCP_OFFLOAD_STATE_CACHED
       structure, followed by a TCP_OFFLOAD_STATE_DELEGATED structure.



#### FilterReservedOffloadState

Reserved for filter drivers.


### -field NextBlock

A pointer to the next NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure at the offload state layer
     (neighbor, path, or TCP) indicated by the 
     <b>Type</b> member of the 
     <b>Header</b> member. NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structures that are linked through 
     <b>NextBlock</b> pointers are always at the same layer of the offload state. A 
     <b>NextBlock</b> value of <b>NULL</b> indicates that there is no additional next
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure at this level.


### -field DependentBlockList

A pointer to an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure that is at a dependent layer of the
     offload state (a higher layer in the offload state tree). 
     





#### For TCP chimney offload:

The 
       <b>DependentBlockList</b> member of an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure at the neighbor layer
       can point only to an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure at the path layer. The 
       <b>DependentBlockList</b> member of an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure at the path layer can
       point only to an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure at the TCP layer. The 
       <b>DependentBlockList</b> member of an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure at the TCP layer is
       always <b>NULL</b>.

A 
     <b>DependentBlockList</b> value of <b>NULL</b> indicates that there is no dependent
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure.


### -field _NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST

 


### -field Status

The completion status of an initiate offload, query offload, update offload, invalidate offload,
     or terminate offload operation that the offload target performed on the state associated with, or
     referenced by, the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. Depending on the operation, NDIS writes
     one of the following NDIS_STATUS values to the 
     <b>Status</b> member:
     





#### NDIS_STATUS_SUCCESS

Initiate offload: The underlying offload target successfully offloaded the state associated with
       the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure and the state associated with all of the immediately
       dependent PROTOCOL_MINIPORT_OFFLOAD_BLOCK_LIST structures.
       

Query, update, invalidate, or terminate offload: The offload target successfully performed the
       operation on the state associated with, or referenced by, the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST
       structure.



#### NDIS_STATUS_OFFLOAD_PARTIAL_SUCCESS

Initiate offload: The underlying offload target successfully offloaded the state associated with
       the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure, but failed to offload the state associated with one or
       more of the immediately dependent NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structures.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_FAILURE

Initiate offload: The underlying offload target failed to offload the state associated with the
       NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. The cause of the failure cannot be categorized.
       

Query, update, invalidate, or terminate offload: The offload target failed to perform the operation
       on the state associated with, or referenced by, the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST
       structure.



#### NDIS_STATUS_RESOURCES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate sufficient
       host memory.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_TCP_ENTRIES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate a TCP
       connection state object.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_PATH_ENTRIES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate a path state
       object.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_NEIGHBOR_ENTRIES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate a neighbor
       state object.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_HW_ADDRESS_ENTRIES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure because the host stack specified a non-<b>NULL</b><b>DlSourceAddress</b> member in the 
       <a href="https://msdn.microsoft.com/1c79a3d6-c365-4740-a2e0-94333b70d8cc">
       NEIGHBOR_OFFLOAD_STATE_CONST</a> structure, and the offload target either does not support
       configurable source MAC addresses or cannot accept additional source MAC addresses.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_IP_ADDRESS_ENTRIES

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate a data
       structure for the source IP address that is referenced by the 
       <b>SourceAddress</b> pointer in the 
       <a href="https://msdn.microsoft.com/a71f70f6-7731-457b-bd6d-b4a649f76f8b">
       PATH_OFFLOAD_STATE_CONST</a> structure.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_TCP_XMIT_BUFFER

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate enough TCP
       transmit buffers.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_TCP_RCV_BUFFER

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure because the offload target could not allocate enough TCP
       receive buffers.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_TCP_RCV_WINDOW

Initiate offload: The offload target failed to offload the state associated with the
       NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure because the 
       <b>InitialRcvWnd</b> member specified in the 
       <a href="https://msdn.microsoft.com/953154eb-e6f3-4013-a68f-1a358953c7ad">
       TCP_OFFLOAD_STATE_CACHED</a> structure is larger than the offload target can support.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_VLAN_ENTRIES

Initiate offload: The offload target has run out of resources for tracking additional VLAN IDs. 
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_VLAN_MISMATCH

Initiate offload: The neighbor 
       <b>VlanId</b> is nonzero and does not match one of the interface VLAN IDs.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.



#### NDIS_STATUS_OFFLOAD_PATH_MTU

Initiate offload: The path MTU for the TCP connection is larger than the offload target
       supports.
       

Query, update, invalidate, or terminate offload: Not an allowed status value.


### -field NdisReserved

Reserved for use by NDIS.


### -field OffloadHandle

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566705">NDIS_OFFLOAD_HANDLE</a> structure. The
     NDIS_OFFLOAD_HANDLE structure represents a protocol or intermediate driver's context for an offloaded
     state object.


### -field ProtocolReserved

Reserved for use by protocol drivers, which can use this area for their own purposes.


### -field MiniportReserved

Reserved for use by offload targets or the miniport portion of an intermediate driver.


### -field ImReserved

Reserved for use by intermediate drivers, which can use this area for their own purposes.


### -field Scratch

The protocol driver or intermediate driver can use this area for internal tracking. The
     information in this area is valid only while the driver has ownership of the 
     <b>
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIS</b> T.


### -field SourceHandle

This member is not significant for a protocol or intermediate driver. A protocol or intermediate
      driver must not modify this member.

When propagating the completion of a state-manipulation operation, an intermediate driver copies the      
      <b>SourceHandle</b> that it stored in its IM call entry to the 
      <b>SourceHandle</b> member of the 
      <a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
      NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that it passes to the NdisMXxxComplete function.


### -field PortNumber

A port number that identifies a miniport adapter port. To assign a miniport adapter port number,
     call the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a> function. A zero
     value identifies the default port of a miniport adapter. Use the default port if the miniport driver has
     not allocated ports for the specified adapter.


### -field NetBufferListChain

When the protocol or intermediate driver specifies a <b>NULL</b> value, 
      <b>NetBufferListChain</b> is not significant and can be ignored by the underlying driver or offload
      target.

When a protocol or intermediate driver specifies a non-<b>NULL</b> value, 
      <b>NetBufferListChain</b> points to a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure that can be a
      stand-alone structure or the first structure in a linked list of such structures. Each NET_BUFFER_LIST
      structure in the linked list describes one 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure. The NET_BUFFER structure
      maps to a chain of memory descriptor lists (MDLs). The NET_BUFFER_LIST and associated structures are
      locked so that they remain resident in physical memory. However, they are not mapped into system
      memory.

The MDLs associated with the NET_BUFFER structures contain data that is being conveyed as part of a
      state-manipulation operation or the completion of such an operation. At present, the linked list can
      contain just one type of data: outstanding send data. For more information about send data, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/handling-outstanding-send-data-during-and-after-an-offload-operation">Handling
      Outstanding Send Data During and After an Offload Operation</a>.

An offload target or intermediate driver can pass outstanding send data to the overlying driver or
      host stack when terminating the offload of a TCP connection. In this case, the offload target specifies
      a non-<b>NULL</b> value for the 
      <b>NetBufferListChain</b> member when calling the 
      <a href="https://msdn.microsoft.com/d444eae5-2e7c-41f2-9fb2-55e172505cf6">
      NdisMTerminateOffloadComplete</a> function. If the offload target is not passing send data for a TCP
      connection that is being terminated, it specifies a <b>NULL</b> value for the 
      <b>NetBufferListChain</b> member.


## -remarks



An intermediate driver creates an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure from an 
    <a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure when 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563771">propagating a
    state-manipulation operation</a>. When 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/propagating-the-completion-of-a-state-manipulation-operation">
    propagating the completion of such an operation</a>, an intermediate driver uses an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure to construct an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure.

An NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure can be immediately followed in memory by an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570939">offload state structure</a> that contains
    the state to be (or that has been) offloaded, queried, updated, invalidated, or terminated. The 
    <b>Type</b> member of the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure's 
    <b>Header</b> specifies the type of offload state, and by implication, the specific offload state
    structure (or structures) that follow the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure in memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568323">NEIGHBOR_OFFLOAD_STATE_CACHED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568324">NEIGHBOR_OFFLOAD_STATE_CONST</a>



<a href="https://msdn.microsoft.com/94a35d0f-3585-45d0-bba8-0b4a8ebbe883">
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562743">NdisInitiateOffload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562774">NdisInvalidateOffload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563771">NdisQueryOffload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564615">NdisTerminateOffload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564646">NdisUpdateOffload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569983">PATH_OFFLOAD_STATE_CACHED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569984">PATH_OFFLOAD_STATE_CONST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569985">PATH_OFFLOAD_STATE_DELEGATED</a>



<a href="https://msdn.microsoft.com/0300d841-b211-42f8-b60d-d7d37201e778">
   ProtocolInitiateOffloadComplete</a>



<a href="https://msdn.microsoft.com/6d2c71d0-9686-4eb5-9715-27de3dc8b390">
   ProtocolInvalidateOffloadComplete</a>



<a href="https://msdn.microsoft.com/f521af88-eb96-4077-8882-9b1d02c6c87c">
   ProtocolQueryOffloadComplete</a>



<a href="https://msdn.microsoft.com/614d36e8-38ac-49a7-8711-7a6c6646309c">
   ProtocolTerminateOffloadComplete</a>



<a href="https://msdn.microsoft.com/3cd7a32a-d560-429b-b191-aeabb87433f3">
   ProtocolUpdateOffloadComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570937">TCP_OFFLOAD_STATE_CACHED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570938">TCP_OFFLOAD_STATE_CONST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570939">TCP_OFFLOAD_STATE_DELEGATED</a>
 

 

