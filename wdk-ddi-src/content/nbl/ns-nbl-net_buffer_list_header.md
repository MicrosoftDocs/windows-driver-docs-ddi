a---
UID: NS:nbl._NET_BUFFER_LIST_HEADER
title: NET_BUFFER_LIST_HEADER
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_LIST_HEADER defines header information for the NET_BUFFER_LIST structure.
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
req.typenames: NET_BUFFER_LIST_HEADER, *PNET_BUFFER_LIST_HEADER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nbl.h
api_name:
 - _NET_BUFFER_LIST_HEADER
 - PNET_BUFFER_LIST_HEADER
 - NET_BUFFER_LIST_HEADER
f1_keywords:
 - _NET_BUFFER_LIST_HEADER
 - nbl/_NET_BUFFER_LIST_HEADER
 - PNET_BUFFER_LIST_HEADER
 - nbl/PNET_BUFFER_LIST_HEADER
 - NET_BUFFER_LIST_HEADER
 - nbl/NET_BUFFER_LIST_HEADER
dev_langs:
 - c++
---


# _NET_BUFFER_LIST_HEADER structure


## -description

The NET_BUFFER_LIST_HEADER defines header information for the 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

## -struct-fields

### -field NetBufferListData

A 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_data">NET_BUFFER_LIST_DATA</a> structure.

### -field Link

Reserved for NDIS.

## -remarks

NDIS maintains the information in the NET_BUFFER_LIST_HEADER union.

## -see-also

<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_data">NET_BUFFER_LIST_DATA</a>
