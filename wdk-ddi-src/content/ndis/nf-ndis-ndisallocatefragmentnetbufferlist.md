---
UID: NF:ndis.NdisAllocateFragmentNetBufferList
title: NdisAllocateFragmentNetBufferList function (ndis.h)
description: Call the NdisAllocateFragmentNetBufferList function to create a new fragmented NET_BUFFER_LIST structure based upon the data in an existing NET_BUFFER_LIST structure.
old-location: netvista\ndisallocatefragmentnetbufferlist.htm
tech.root: netvista
ms.assetid: 40b6596b-7ab8-4336-8c38-21b9f32d8558
ms.date: 05/02/2018
keywords: ["NdisAllocateFragmentNetBufferList function"]
ms.keywords: NdisAllocateFragmentNetBufferList, NdisAllocateFragmentNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateFragmentNetBufferList, ndis_netbuf_functions_ref_9155bd3d-f4c1-4655-b9a3-256ff64093cf.xml, netvista.ndisallocatefragmentnetbufferlist
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisAllocateFragmentNetBufferList
 - ndis/NdisAllocateFragmentNetBufferList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisAllocateFragmentNetBufferList
---

# NdisAllocateFragmentNetBufferList function


## -description

Call the 
  <b>NdisAllocateFragmentNetBufferList</b> function to create a new fragmented 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure based upon the data
  in an existing NET_BUFFER_LIST structure.

## -parameters

### -param OriginalNetBufferList 

[in]
A pointer to an existing NET_BUFFER_LIST structure.

### -param NetBufferListPool

A handle that was obtained from a call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
     NdisAllocateNetBufferListPool</a> function.

### -param NetBufferPool

A NET_BUFFER structure pool handle that was previously returned from a call to 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">
     NdisAllocateNetBufferPool</a>.

### -param StartOffset 

[in]
An additional byte offset from the start of the data in each 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure. This offset is in addition
     to the value of the 
     <b>DataOffset</b> member specified in each NET_BUFFER structure.

### -param MaximumLength 

[in]
The maximum length, in bytes, for each fragment in the new NET_BUFFER_LIST structure. Each
     fragment is described by a NET_BUFFER structure.

### -param DataOffsetDelta 

[in]
The additional amount of 
     <i>used data space</i> that NDIS should make available in the new NET_BUFFER structures.

### -param DataBackFill 

[in]
The amount of data space in addition to the value of the 
     <i>DataOffsetDelta</i> parameter to allocate if allocation is necessary. If NDIS must allocate memory to
     supply the data space requested in 
     <i>DataOffsetDelta</i>, it should also allocate the additional space that 
     <i>DataBackFill</i> specifies.

### -param AllocateFragmentFlags 

[in]
NDIS flags that can be combined with an OR operation. Set this parameter to zero. There are
     currently no flags defined for this function.

## -returns

<b>NdisAllocateFragmentNetBufferList</b> returns a pointer to a new fragmented NET_BUFFER_LIST structure.
     If the allocation failed, the return value is <b>NULL</b>.

## -remarks

<b>NdisAllocateFragmentNetBufferList</b> allocates and initializes a new fragment 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure and 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures that describe the same data
    that is described by the NET_BUFFER_LIST structure that the caller passed to 
    <b>NdisAllocateFragmentNetBufferList</b>.

If the fragment NET_BUFFER_LIST structure should have attributes that are associated with a given
    pool, the caller must specify the pool handle in the 
    <i>NetBufferListPoolHandle</i> or 
    <i>NetBufferPoolHandle</i> parameter. For example, the 
    <b>ProtocolType</b> member of the NET_BUFFER_LIST structure is associated with the pool.

For each NET_BUFFER structure in the specified source NET_BUFFER_LIST structure, NDIS creates the
    fragment NET_BUFFER structures as follows:

<ul>
<li>
NDIS creates the fragments starting from the beginning of the 
      <i>used data space</i> in the source NET_BUFFER structure and offset by the value specified in the 
      <i>StartOffset</i> parameter.

</li>
<li>
NDIS divides the 
      <i>used data space</i>(after accounting for the 
      <i>StartOffset</i> ) in the source NET_BUFFER structure into fragments.

</li>
<li>
The length of the 
      <i>used data space</i> of each fragment is less than or equal to the value specified in the 
      <i>MaximumLength</i> parameter. The 
      <i>used data space</i> of the last fragment can be less than 
      <i>MaximumLength</i> .

</li>
<li>
Each fragment is described by a new NET_BUFFER structure and a new set of MDL chains.

</li>
<li>
The data offset of the new NET_BUFFER structures is retreated (the value of the 
      <b>DataOffset</b> member is reduced) by the number of bytes specified in the 
      <i>DataOffsetDelta</i> parameter.

</li>
<li>
If NDIS must allocate memory to supply the data space requested in 
      <i>DataOffsetDelta</i>, it should also allocate the additional space that 
      <i>DataBackFill</i> specifies.

</li>
</ul>
The new fragment NET_BUFFER_LIST structure that 
    <b>NdisAllocateFragmentNetBufferList</b> creates does not include an initial 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">
    NET_BUFFER_LIST_CONTEXT</a> structure.

Call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreefragmentnetbufferlist">
    NdisFreeFragmentNetBufferList</a> function to free a NET_BUFFER_LIST structure and all associated
    NET_BUFFER structures and MDL chains that were previously allocated by calling 
    <b>NdisAllocateFragmentNetBufferList</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">NdisAllocateNetBufferPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreefragmentnetbufferlist">
   NdisFreeFragmentNetBufferList</a>