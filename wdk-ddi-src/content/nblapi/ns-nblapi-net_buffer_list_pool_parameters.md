---
UID: NS:nblapi._NET_BUFFER_LIST_POOL_PARAMETERS
title: NET_BUFFER_LIST_POOL_PARAMETERS
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_LIST_POOL_PARAMETERS structure defines the parameters for a pool of NET_BUFFER_LIST structures.
tech.root: netvista
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndis/nblapi.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: NET_BUFFER_LIST_POOL_PARAMETERS, *PNET_BUFFER_LIST_POOL_PARAMETERS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nblapi.h
api_name:
 - _NET_BUFFER_LIST_POOL_PARAMETERS
 - PNET_BUFFER_LIST_POOL_PARAMETERS
 - NET_BUFFER_LIST_POOL_PARAMETERS
f1_keywords:
 - _NET_BUFFER_LIST_POOL_PARAMETERS
 - nblapi/_NET_BUFFER_LIST_POOL_PARAMETERS
 - PNET_BUFFER_LIST_POOL_PARAMETERS
 - nblapi/PNET_BUFFER_LIST_POOL_PARAMETERS
 - NET_BUFFER_LIST_POOL_PARAMETERS
 - nblapi/NET_BUFFER_LIST_POOL_PARAMETERS
dev_langs:
 - c++
---


# _NET_BUFFER_LIST_POOL_PARAMETERS structure


## -description

The <b>NET_BUFFER_LIST_POOL_PARAMETERS</b> structure defines the parameters for a pool of <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NET_BUFFER_LIST_POOL_PARAMETERS</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NET_BUFFER_LIST_POOL_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NET_BUFFER_LIST_POOL_PARAMETERS_REVISION_1

Original version for NDIS 6.0.

Set the <b>Size</b> member to NDIS_SIZEOF_NET_BUFFER_LIST_POOL_PARAMETERS_REVISION_1.

### -field ProtocolId

The type of caller. Miniport, filter, and intermediate drivers set this field to zero
       (NDIS_PROTOCOL_ID_DEFAULT). Protocol drivers use one of the following values:
       





#### NDIS_PROTOCOL_ID_DEFAULT

Specifies a default protocol driver identifier.



#### NDIS_PROTOCOL_ID_TCP_IP

Specifies the TCP/IP protocol.



#### NDIS_PROTOCOL_ID_IPX

Specifies the IPX protocol.



#### NDIS_PROTOCOL_ID_NBF

Specifies the NetBEUI protocol.

### -field fAllocateNetBuffer

If this member is set to TRUE, NDIS allocates a pool of <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures. Each allocated <b>NET_BUFFER_LIST</b> structure is initialized with one 
       <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure. 

If this member is set to FALSE, NDIS allocates a pool of <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures. Each allocated <b>NET_BUFFER_LIST</b> structure is not initialized  to contain any 
       <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures.

For more information, see the Remarks section.

### -field ContextSize

The size, in bytes, of the preallocated 
       <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a> structure
       data that NDIS should provide for the NET_BUFFER_LIST structures in this pool. The 
       <b>ContextSize</b> must be a multiple of the value that is defined by MEMORY_ALLOCATION_ALIGNMENT.

### -field PoolTag

A kernel pool tag that the caller uses when it allocates NET_BUFFER_LIST structures from this
       pool. The tag is a string, delimited by single quotation marks, with up to four characters, usually
       specified in reversed order. The kernel pool tag helps NDIS to identify the owner of the
       <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures that are allocated from this pool.

### -field DataSize

The default data size, in bytes, for data buffers that are associated with this 
       <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> pool, if any. NDIS uses
       this value to set the size of any data buffers that it allocates for any associated 
       <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures. 
       

For more information, see the Remarks section.

## -remarks

If 
       <b>fAllocateNetBuffer</b> is set to FALSE, NDIS will not allocate <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures, and 
       <b>DataSize</b> should be set to zero.

If 
       <b>DataSize</b> is not zero, 
       <b>fAllocateNetBuffer</b> must be set to TRUE. This causes NDIS to allocate the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure with a data buffer
       of the specified size.

If 
       <b>DataSize</b> is zero and 
       <b>fAllocateNetBuffer</b> is <b>TRUE</b>, NDIS allocates the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure but not the data
       buffer.

The <i>Parameters</i> parameter of the <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">NdisAllocateNetBufferListPool</a> function contains a pointer to an <b>NET_BUFFER_LIST_POOL_PARAMETERS</b> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_data">NET_BUFFER_LIST_DATA</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">NdisAllocateNetBufferListPool</a>