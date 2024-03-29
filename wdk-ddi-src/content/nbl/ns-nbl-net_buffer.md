---
UID: NS:nbl._NET_BUFFER
title: NET_BUFFER
ms.date: 11/30/2020
targetos: Windows
description: The NET_BUFFER structure specifies data that is transmitted or received over the network.
tech.root: netvista
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndis/nbl.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: NET_BUFFER, *PNET_BUFFER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nbl.h
api_name:
 - _NET_BUFFER
 - PNET_BUFFER
 - NET_BUFFER
f1_keywords:
 - _NET_BUFFER
 - nbl/_NET_BUFFER
 - PNET_BUFFER
 - nbl/PNET_BUFFER
 - NET_BUFFER
 - nbl/NET_BUFFER
dev_langs:
 - c++
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
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_header">NET_BUFFER_HEADER</a> structure. This is a duplicate of the above union, for compatibility reasons.

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
      <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure that is
      associated with the NET_BUFFER.

<div class="alert"><b>Note</b>  A miniport driver can set the 
      <b>DataPhysicalAddress</b> member of the NET_BUFFER structure, even if the structure is not associated
      with a split frame. In this case, 
      <b>DataPhysicalAddress</b> contains the physical address of the header MDL.</div>
<div> </div>

### -field SharedMemoryInfo

A pointer to an 
      <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_shared_memory">
      NET_BUFFER_SHARED_MEMORY</a> structure.

### -field ScatterGatherList

The SCATTER_GATHER_LIST structure describes a scatter/gather list for DMA.

## -remarks

NDIS drivers can call the following functions to allocate and initialize a NET_BUFFER structure:

<ul>
<li>

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
       NdisAllocateNetBufferAndNetBufferList</a>


</li>
</ul>
NDIS drivers can call the 
    <a href="/windows-hardware/drivers/ddi/nblapi/nf-nblapi-ndisallocatenetbufferlistpool">
    NdisAllocateNetBufferListPool</a> function and then set the 
    <b>fAllocateNetBuffer</b> member of the 
    <a href="/windows-hardware/drivers/ddi/nblapi/ns-nblapi-net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure to <b>TRUE</b> when allocating a 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure pool. In this
    case, a NET_BUFFER structure is preallocated with each NET_BUFFER_LIST structure that the driver
    allocates from the pool.

Chained to each NET_BUFFER structure are one or more buffer descriptors that map buffers that contain
    network packet data. These buffer descriptors are specified as an MDL chain in the 
    <b>NetBufferHeader</b> member. Such network packet data either was received or will be transmitted.

To access additional data space in the MDL chain, NDIS drivers can call the following functions:

<ul>
<li>

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
       NdisRetreatNetBufferDataStart</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferlistdatastart">
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


<a href="/windows-hardware/drivers/network/net-buffer-next-nb">NET_BUFFER_NEXT_NB</a>



<a href="/windows-hardware/drivers/network/net-buffer-first-mdl">NET_BUFFER_FIRST_MDL</a>



<a href="/windows-hardware/drivers/network/net-buffer-data-offset">NET_BUFFER_DATA_OFFSET</a>



<a href="/windows-hardware/drivers/network/net-buffer-data-length">NET_BUFFER_DATA_LENGTH</a>



<a href="/windows-hardware/drivers/network/net-buffer-protocol-reserved">NET_BUFFER_PROTOCOL_RESERVED</a>



<a href="/windows-hardware/drivers/network/net-buffer-miniport-reserved">NET_BUFFER_MINIPORT_RESERVED</a>



<a href="/windows-hardware/drivers/network/net-buffer-checksum-bias">NET_BUFFER_CHECKSUM_BIAS</a>



<a href="/windows-hardware/drivers/network/net-buffer-current-mdl">NET_BUFFER_CURRENT_MDL</a>



<a href="/windows-hardware/drivers/network/net-buffer-current-mdl-offset">
       NET_BUFFER_CURRENT_MDL_OFFSET</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetpoolfromnetbuffer">NdisGetPoolFromNetBuffer</a>


For more information on how to use net buffers, see 
    <a href="/windows-hardware/drivers/network/net-buffer-architecture">NET_BUFFER Architecture</a>.

## -see-also

<a href="/windows-hardware/drivers/network/net-buffer-checksum-bias">NET_BUFFER_CHECKSUM_BIAS</a>



<a href="/windows-hardware/drivers/network/net-buffer-current-mdl">NET_BUFFER_CURRENT_MDL</a>



<a href="/windows-hardware/drivers/network/net-buffer-current-mdl-offset">NET_BUFFER_CURRENT_MDL_OFFSET</a>



<a href="/windows-hardware/drivers/network/net-buffer-data-length">NET_BUFFER_DATA_LENGTH</a>



<a href="/windows-hardware/drivers/network/net-buffer-data-offset">NET_BUFFER_DATA_OFFSET</a>



<a href="/windows-hardware/drivers/network/net-buffer-first-mdl">NET_BUFFER_FIRST_MDL</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_header">NET_BUFFER_HEADER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/nblapi/ns-nblapi-net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="/windows-hardware/drivers/network/net-buffer-miniport-reserved">NET_BUFFER_MINIPORT_RESERVED</a>



<a href="/windows-hardware/drivers/network/net-buffer-next-nb">NET_BUFFER_NEXT_NB</a>



<a href="/windows-hardware/drivers/network/net-buffer-protocol-reserved">NET_BUFFER_PROTOCOL_RESERVED</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="/windows-hardware/drivers/ddi/nblapi/nf-nblapi-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetpoolfromnetbuffer">NdisGetPoolFromNetBuffer</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsendnetbufferlistscomplete">
   NdisMSendNetBufferListsComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
   NdisRetreatNetBufferDataStart</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferlistdatastart">
   NdisRetreatNetBufferListDataStart</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a>

