---
UID: NF:nblapi.NdisAdjustNetBufferCurrentMdl
title: NdisAdjustNetBufferCurrentMdl
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NdisAdjustNetBufferCurrentMdl function updates a NET_BUFFER structure based on the current data offset.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis/nblapi.h
req.idl: 
req.include-header: ndis.h
req.irql: Any level (see Remarks section)
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
 - NdisAdjustNetBufferCurrentMdl
f1_keywords:
 - NdisAdjustNetBufferCurrentMdl
 - nblapi/NdisAdjustNetBufferCurrentMdl
dev_langs:
 - c++
---


# NdisAdjustNetBufferCurrentMdl function


## -description

The 
  <b>NdisAdjustNetBufferCurrentMdl</b> function updates a 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure based on the current data
  offset.

## -parameters

### -param NetBuffer 

[in]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

## -remarks

The 
    <b>NdisAdjustNetBufferCurrentMdl</b> function recalculates and sets the 
    <b>CurrentMdl</b> and 
    <b>CurrentMdlOffset</b> members of a 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure based on the 
    <b>DataOffset</b> member of the NET_BUFFER structure.

Callers of 
    <b>NdisAdjustNetBufferCurrentMdl</b> can run at any IRQL, but typically run at IRQL <=
    DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>