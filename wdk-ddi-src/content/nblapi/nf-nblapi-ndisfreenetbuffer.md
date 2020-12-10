<<<<<<< HEAD:wdk-ddi-src/content/nblapi/nf-nblapi-ndisfreenetbuffer.md
---
UID: NF:nblapi.NdisFreeNetBuffer
title: NdisFreeNetBuffer
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisFreeNetBuffer function to free a NET_BUFFER structure that was previously allocated from a NET_BUFFER structure pool with the NdisAllocateNetBuffer function.
tech.root: netvista 
req.assembly: 
req.construct-type: function
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateNetBuffer
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
 - NdisFreeNetBuffer
f1_keywords:
 - NdisFreeNetBuffer
 - nblapi/NdisFreeNetBuffer
dev_langs:
 - c++
---

# NdisFreeNetBuffer function


## -description

Call the 
  <b>NdisFreeNetBuffer</b> function to free a 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure that was previously allocated
  from a NET_BUFFER structure pool with the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a> function.

## -parameters

### -param NetBuffer 

[in]
A pointer to a NET_BUFFER structure that was allocated by calling 
     <b>NdisAllocateNetBuffer</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>

=======
---
UID: NF:ndis.NdisFreeNetBuffer
title: NdisFreeNetBuffer function (ndis.h)
description: Call the NdisFreeNetBuffer function to free a NET_BUFFER structure that was previously allocated from a NET_BUFFER structure pool with the NdisAllocateNetBuffer function.
old-location: netvista\ndisfreenetbuffer.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFreeNetBuffer function"]
ms.keywords: NdisFreeNetBuffer, NdisFreeNetBuffer function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBuffer, ndis_netbuf_functions_ref_623498b1-25e0-48ae-831e-8c1240106bd4.xml, netvista.ndisfreenetbuffer
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateNetBuffer
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
 - NdisFreeNetBuffer
 - ndis/NdisFreeNetBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFreeNetBuffer
---

# NdisFreeNetBuffer function


## -description

Call the 
  <b>NdisFreeNetBuffer</b> function to free a 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure that was previously allocated
  from a NET_BUFFER structure pool with the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a> function.

## -parameters

### -param NetBuffer 

[in]
A pointer to a NET_BUFFER structure that was allocated by calling 
     <b>NdisAllocateNetBuffer</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>
>>>>>>> release-iron:wdk-ddi-src/content/ndis/nf-ndis-ndisfreenetbuffer.md
