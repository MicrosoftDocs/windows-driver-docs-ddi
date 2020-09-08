---
UID: NF:ndis.NdisFreeReassembledNetBufferList
title: NdisFreeReassembledNetBufferList function (ndis.h)
description: Call the NdisFreeReassembledNetBufferList function to free a reassembled NET_BUFFER_LIST structure and the associated NET_BUFFER structure and MDL chain.
old-location: netvista\ndisfreereassemblednetbufferlist.htm
tech.root: netvista
ms.assetid: bcbb0c56-1500-45b2-bd20-03726ef7da77
ms.date: 05/02/2018
keywords: ["NdisFreeReassembledNetBufferList function"]
ms.keywords: NdisFreeReassembledNetBufferList, NdisFreeReassembledNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisFreeReassembledNetBufferList, ndis_netbuf_functions_ref_604900da-90fb-4986-880e-8fea63c240a0.xml, netvista.ndisfreereassemblednetbufferlist
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
 - NdisFreeReassembledNetBufferList
 - ndis/NdisFreeReassembledNetBufferList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFreeReassembledNetBufferList
---

# NdisFreeReassembledNetBufferList function


## -description

Call the 
  <b>NdisFreeReassembledNetBufferList</b> function to free a reassembled 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure and the associated 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure and MDL chain.

## -parameters

### -param ReassembledNetBufferList 

[in]
A pointer to a NET_BUFFER_LIST structure that the driver allocated by calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatereassemblednetbufferlist">
     NdisAllocateReassembledNetBufferList</a> function.

### -param DataOffsetDelta 

[in]
The number of bytes to advance (add to) the 
     <b>DataOffset</b> member of the reassembled NET_BUFFER structure before freeing the structure. This value
     should match 
     <i>DataOffsetDelta</i> that the driver passed to 
     <b>NdisAllocateReassembledNetBufferList</b>.

### -param FreeReassembleFlags 

[in]
NDIS flags that can be combined with an OR operation. Set this parameter to zero. There are
     currently no flags defined for this function.

## -remarks

<b>NdisFreeReassembledNetBufferList</b> frees a reassembled 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that the caller
    allocated by calling 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatereassemblednetbufferlist">
    NdisAllocateReassembledNetBufferList</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatereassemblednetbufferlist">
   NdisAllocateReassembledNetBufferList</a>

