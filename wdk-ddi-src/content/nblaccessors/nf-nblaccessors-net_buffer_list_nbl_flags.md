---
UID: NF:nblaccessors.NET_BUFFER_LIST_NBL_FLAGS
title: NET_BUFFER_LIST_NBL_FLAGS
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_LIST_NBL_FLAGS macro retrieves the NblFlags member of a NET_BUFFER_LIST structure.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis/nblaccessors.h
req.idl: 
req.include-header: ndis.h
req.irql: 
req.kmdf-ver: 
req.lib: 
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
 - HeaderDef
api_location:
 - nblaccessors.h
api_name:
 - NET_BUFFER_LIST_NBL_FLAGS
f1_keywords:
 - NET_BUFFER_LIST_NBL_FLAGS
 - nblaccessors/NET_BUFFER_LIST_NBL_FLAGS
dev_langs:
 - c++
---

# NET_BUFFER_LIST_NBL_FLAGS macro


## -description

The **NET_BUFFER_LIST_NBL_FLAGS** macro retrieves the **NblFlags** member of a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -remarks

NDIS network drivers should use the **NET_BUFFER_LIST_NBL_FLAGS** macro to get the **NblFlags** member of a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)
