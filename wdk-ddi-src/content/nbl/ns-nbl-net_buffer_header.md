---
UID: NS:nbl._NET_BUFFER_HEADER
title: NET_BUFFER_HEADER
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_HEADER structure specifies header information for the NET_BUFFER structure.
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
req.typenames: NET_BUFFER_HEADER, *PNET_BUFFER_HEADER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nbl.h
api_name:
 - _NET_BUFFER_HEADER
 - PNET_BUFFER_HEADER
 - NET_BUFFER_HEADER
f1_keywords:
 - _NET_BUFFER_HEADER
 - nbl/_NET_BUFFER_HEADER
 - PNET_BUFFER_HEADER
 - nbl/PNET_BUFFER_HEADER
 - NET_BUFFER_HEADER
 - nbl/NET_BUFFER_HEADER
dev_langs:
 - c++
---

# _NET_BUFFER_HEADER structure


## -description

The NET_BUFFER_HEADER structure specifies header information for the 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

## -struct-fields

### -field NetBufferData

A 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_data">NET_BUFFER_DATA</a> structure.

### -field Link

Reserved for NDIS.

## -remarks

NDIS maintains the information in the NET_BUFFER_HEADER union.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_data">NET_BUFFER_DATA</a>

