---
UID: NS:nbl._NET_BUFFER_LIST_DATA
title: NET_BUFFER_LIST_DATA
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_LIST_DATA structure contains management data for the NET_BUFFER structures that are linked to a NET_BUFFER_LIST structure.
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
req.typenames: NET_BUFFER_LIST_DATA, *PNET_BUFFER_LIST_DATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nbl.h
api_name:
 - _NET_BUFFER_LIST_DATA
 - PNET_BUFFER_LIST_DATA
 - NET_BUFFER_LIST_DATA
f1_keywords:
 - _NET_BUFFER_LIST_DATA
 - nbl/_NET_BUFFER_LIST_DATA
 - PNET_BUFFER_LIST_DATA
 - nbl/PNET_BUFFER_LIST_DATA
 - NET_BUFFER_LIST_DATA
 - nbl/NET_BUFFER_LIST_DATA
dev_langs:
 - c++
---

# _NET_BUFFER_LIST_DATA structure


## -description

The NET_BUFFER_LIST_DATA structure contains management data for the 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures that are linked to a 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

## -struct-fields

### -field Next

A pointer to the next NET_BUFFER_LIST structure in a linked list of NET_BUFFER_LIST structures. If
     this structure is the last NET_BUFFER_LIST structure in the list, this member is <b>NULL</b>.

### -field FirstNetBuffer

A pointer to the first 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure in the linked list of
     NET_BUFFER structures.

## -remarks

The 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_header">NET_BUFFER_LIST_HEADER</a> structure
    contains a NET_BUFFER_LIST_DATA structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_header">NET_BUFFER_LIST_HEADER</a>

