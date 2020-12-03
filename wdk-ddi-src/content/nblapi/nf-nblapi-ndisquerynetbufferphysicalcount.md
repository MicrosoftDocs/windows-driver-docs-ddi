---
UID: NF:nblapi.NdisQueryNetBufferPhysicalCount
title: NdisQueryNetBufferPhysicalCount
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NdisQueryNetBufferPhysicalCount function returns the maximum number of physical breaks mapped by the buffer descriptors that are associated with the given NET_BUFFER structure.
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
 - NdisQueryNetBufferPhysicalCount
f1_keywords:
 - NdisQueryNetBufferPhysicalCount
 - nblapi/NdisQueryNetBufferPhysicalCount
dev_langs:
 - c++
---

# NdisQueryNetBufferPhysicalCount function


## -description

The 
  <b>NdisQueryNetBufferPhysicalCount</b> function returns the maximum number of physical breaks mapped by the
  buffer descriptors that are associated with the given 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

## -parameters

### -param NetBuffer 

[in]
A pointer to a previously allocated 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

## -returns

<b>NdisQueryNetBufferPhysicalCount</b> returns a ULONG value containing a count of the maximum number of
     physical breaks, mapped by MDLs that are associated with the specified NET_BUFFER structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>