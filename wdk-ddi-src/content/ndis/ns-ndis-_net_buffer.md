---
UID: NS:ndis._NET_BUFFER
title: _NET_BUFFER (ndis.h)
description: The NET_BUFFER structure specifies data that is transmitted or received over the network.
old-location: netvista\net_buffer.htm
tech.root: netvista
ms.assetid: 66a725f9-ae72-41b4-8840-63c9ff89ace7
ms.date: 10/31/2019
keywords: ["NET_BUFFER structure"]
ms.keywords: "*PNET_BUFFER, NET_BUFFER, NET_BUFFER structure [Network Drivers Starting with Windows Vista], PNET_BUFFER, PNET_BUFFER structure pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER, ndis/NET_BUFFER, ndis/PNET_BUFFER, ndis_netbuf_structures_ref_e07734b2-9135-48a5-b3d4-f6e252a52c45.xml, netvista.net_buffer"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
targetos: Windows
req.typenames: NET_BUFFER, *PNET_BUFFER
f1_keywords:
 - _NET_BUFFER
 - ndis/_NET_BUFFER
 - PNET_BUFFER
 - ndis/PNET_BUFFER
 - NET_BUFFER
 - ndis/NET_BUFFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NET_BUFFER
---

# _NET_BUFFER structure


## -description

The NET_BUFFER structure specifies data that is transmitted or received over the network.

## -struct-fields

### -field Next

A pointer to the next NET_BUFFER structure in a linked list of NET_BUFFER structures. If this structure is the last NET_BUFFER structure in the list, this member is NULL.

### -field CurrentMdl

A pointer to the first MDL that the current driver is using. This member provides an optimization that improves performance by skipping over any MDLs that the current driver is not using.

### -field CurrentMdlOffset

The offset, in bytes, to the beginning of the *used data space* in the MDL that is specified by the **CurrentMdl** member.

### -field DataLength

The length, in bytes, of the used data space in the MDL chain. The maximum length is 0xFFFFFFFF bytes.

### -field stDataLength

The length, in bytes, of the used data space in the MDL chain. The maximum length is 0xFFFFFFFF bytes. This member is the same as **DataLength**, but its type is **SIZE_T** instead of **ULONG**.

### -field MdlChain

A pointer to a linked list of MDLs that map a data buffer. The data buffer stores the network data.

### -field DataOffset

The offset, in bytes, from the beginning of the MDL chain to the beginning of the network data in the MDL chain. This offset is also the size, in bytes, of the *unused data space*.

### -field Link

Reserved for NDIS.

### -field NetBufferHeader

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_header">NET_BUFFER_HEADER</a> structure. This is a duplicate of the above union, for compatibility reasons.

### -field ChecksumBias

The number of bytes to skip over from the beginning of the data buffer when computing a checksum.
     This member is used by the TCP/IP protocol.

### -field Reserved

Reserved for future use.

### -field NdisPoolHandle

A pool handle that identifies the NET_BUFFER pool from which the NET_BUFFER structure was
     allocated.

### -field NdisReserved

Reserved for NDIS.

### -field ProtocolReserved

Reserved for use by protocol drivers. Protocol drivers and NDIS intermediate drivers can use this
     area for their own purposes. Intermediate drivers can use this member only if it is not already in
     use.

### -field MiniportReserved

Reserved for use by miniport drivers. Miniport drivers and NDIS intermediate drivers can use this
     area for their own purposes.

### -field DataPhysicalAddress

<div class="alert"><b>Note</b>  The name of this member is 
      <b>NdisReserved1</b> for NDIS 6.0 drivers and is 
      <b>DataPhysicalAddress</b> for NDIS 6.1 and later drivers. For NDIS 6.0 drivers, this member is reserved
      for NDIS.</div>
<div> </div>
The physical address of the data portion of a frame. This member should be to zero if the driver
      that allocated NET_BUFFER does not specify the address. This member is valid only if the
      NDIS_NBL_FLAGS_SPLIT_AT_UPPER_LAYER_PROTOCOL_HEADER or
      NDIS_NBL_FLAGS_SPLIT_AT_UPPER_LAYER_PROTOCOL_PAYLOAD flag is set in the 
      <b>NblFlags</b> member of the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that is
      associated with the NET_BUFFER.

<div class="alert"><b>Note</b>  A miniport driver can set the 
      <b>DataPhysicalAddress</b> member of the NET_BUFFER structure, even if the structure is not associated
      with a split frame. In this case, 
      <b>DataPhysicalAddress</b> contains the physical address of the header MDL.</div>
<div> </div>

### -field SharedMemoryInfo

A pointer to an 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_shared_memory">
      NET_BUFFER_SHARED_MEMORY</a> structure.

### -field ScatterGatherList

The SCATTER_GATHER_LIST structure describes a scatter/gather list for DMA.

## -remarks

NDIS drivers can call the following functions to allocate and initialize a NET_BUFFER structure:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
       NdisAllocateNetBufferAndNetBufferList</a>


</li>
</ul>
NDIS drivers can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
    NdisAllocateNetBufferListPool</a> function and then set the 
    <b>fAllocateNetBuffer</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure to <b>TRUE</b> when allocating a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure pool. In this
    case, a NET_BUFFER structure is preallocated with each NET_BUFFER_LIST structure that the driver
    allocates from the pool.

Chained to each NET_BUFFER structure are one or more buffer descriptors that map buffers that contain
    network packet data. These buffer descriptors are specified as an MDL chain in the 
    <b>NetBufferHeader</b> member. Such network packet data either was received or will be transmitted.

To access additional data space in the MDL chain, NDIS drivers can call the following functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
       NdisRetreatNetBufferDataStart</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferlistdatastart">
       NdisRetreatNetBufferListDataStart</a>


</li>
</ul>
NDIS drivers typically use the 
    <b>MiniportReserved</b> or 
    <b>ProtocolReserved</b> members of the NET_BUFFER structure to maintain NET_BUFFER structure context
    information.

<div class="alert"><b>Note</b>  Only one driver can use 
    <b>MiniportReserved</b> or 
    <b>ProtocolReserved</b> members. Therefore, if another driver has used either of these members, an
    intermediate driver cannot use them.</div>
<div> </div>
To access members of the NET_BUFFER structure, use the following macros and functions:


<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-next-nb">NET_BUFFER_NEXT_NB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-first-mdl">NET_BUFFER_FIRST_MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-data-offset">NET_BUFFER_DATA_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-data-length">NET_BUFFER_DATA_LENGTH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-protocol-reserved">NET_BUFFER_PROTOCOL_RESERVED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-miniport-reserved">NET_BUFFER_MINIPORT_RESERVED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-checksum-bias">NET_BUFFER_CHECKSUM_BIAS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-current-mdl">NET_BUFFER_CURRENT_MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-current-mdl-offset">
       NET_BUFFER_CURRENT_MDL_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetpoolfromnetbuffer">NdisGetPoolFromNetBuffer</a>


For more information on how to use net buffers, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-architecture">NET_BUFFER Architecture</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-checksum-bias">NET_BUFFER_CHECKSUM_BIAS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-current-mdl">NET_BUFFER_CURRENT_MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-current-mdl-offset">NET_BUFFER_CURRENT_MDL_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-data-length">NET_BUFFER_DATA_LENGTH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-data-offset">NET_BUFFER_DATA_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-first-mdl">NET_BUFFER_FIRST_MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_header">NET_BUFFER_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-miniport-reserved">NET_BUFFER_MINIPORT_RESERVED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-next-nb">NET_BUFFER_NEXT_NB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-protocol-reserved">NET_BUFFER_PROTOCOL_RESERVED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetpoolfromnetbuffer">NdisGetPoolFromNetBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsendnetbufferlistscomplete">
   NdisMSendNetBufferListsComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
   NdisRetreatNetBufferDataStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferlistdatastart">
   NdisRetreatNetBufferListDataStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a>

