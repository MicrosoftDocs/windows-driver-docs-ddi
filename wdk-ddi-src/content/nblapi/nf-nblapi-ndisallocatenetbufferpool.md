---
UID: NF:nblapi.NdisAllocateNetBufferPool
title: NdisAllocateNetBufferPool
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisAllocateNetBufferPool function to allocate a pool of NET_BUFFER structures.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: Irql_NetBuffer_Function
req.dll: 
req.header: ndis/nblapi.h
req.idl: 
req.include-header: ndis.h
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: Ndis.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - nblapi.h
api_name:
 - NdisAllocateNetBufferPool
f1_keywords:
 - NdisAllocateNetBufferPool
 - nblapi/NdisAllocateNetBufferPool
dev_langs:
 - c++
---

# NdisAllocateNetBufferPool function


## -description

Call the
  <b>NdisAllocateNetBufferPool</b> function to allocate a pool of 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures.

## -parameters

### -param NdisHandle 

[in, optional]
An NDIS handle that was obtained during caller initialization.

### -param Parameters 

[in]
A pointer to a NET_BUFFER_POOL_PARAMETERS structure that defines the parameters for the pool. The
     structure is defined as follows:
     


```
typedef struct _NET_BUFFER_POOL_PARAMETERS {
  NDIS_OBJECT_HEADER  Header;
  ULONG  PoolTag;
  ULONG  DataSize;
} NET_BUFFER_POOL_PARAMETERS, *PNET_BUFFER_POOL_PARAMETERS;
```

This structure includes the following members:





#### Header

The 
       <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
       NET_BUFFER_POOL_PARAMETERS structure. Set the 
       <b>Type</b> member of the structure that 
       <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
       <b>Revision</b> member to NET_BUFFER_POOL_PARAMETERS_REVISION_1, and the 
       <b>Size</b> member to NDIS_SIZEOF_NET_BUFFER_POOL_PARAMETERS_REVISION_1.



#### PoolTag

A kernel pool tag that the caller uses when it allocates 
       <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures from this pool. The tag
       is a string, delimited by single quotation marks, with up to four characters, usually specified in
       reverse order. The kernel pool tag helps NDIS to identify the owner of the NET_BUFFER structures that
       are allocated from this pool.



#### DataSize

The default data size for data buffers associated with this pool. The caller must set this value
       if it calls the 
       <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffermdlanddata">
       NdisAllocateNetBufferMdlAndData</a> function. NDIS uses this value to set the size of the data
       buffer that it allocates for the NET_BUFFER structure. If the caller does not use this feature, this
       value should be set to zero.

## -returns

<b>NdisAllocateNetBufferPool</b> returns a handle to the NET_BUFFER structure pool that NDIS allocates.
     If the allocation was unsuccessful, this handle is <b>NULL</b>. This handle is a required parameter in
     subsequent calls to NDIS functions that allocate and free NET_BUFFER structures from this pool.

## -remarks

Call the following functions to allocate 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures from the NET_BUFFER
    structure pool.


<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffermdlanddata">
       NdisAllocateNetBufferMdlAndData</a>


<div class="alert"><b>Note</b>  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> and 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures must be allocated
    from an NDIS buffer pool. A driver must not allocate and initialize a NET_BUFFER or NET_BUFFER_LIST
    structure from its private memory pool or the stack.</div>
<div> </div>
You can call 
    <b>NdisAllocateNetBufferPool</b> and set the 
    <b>DataSize</b> value when creating a NET_BUFFER structure pool. In this case, MDL and data are
    preallocated with each NET_BUFFER structure that the caller allocates from the pool. You must call the 
    <b>NdisAllocateNetBufferMdlAndData</b> function to allocate NET_BUFFER structures from such a pool.

MDL and data buffers that are allocated with 
    <b>NdisAllocateNetBufferMdlAndData</b> should not be freed separate from the NET_BUFFER structure. Such
    structures are freed with the NET_BUFFER structure when you call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a> function.

Call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferpool">NdisFreeNetBufferPool</a> function to
    free NET_BUFFER structure pools that are created with 
    <b>NdisAllocateNetBufferPool</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffermdlanddata">
   NdisAllocateNetBufferMdlAndData</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferpool">NdisFreeNetBufferPool</a>

