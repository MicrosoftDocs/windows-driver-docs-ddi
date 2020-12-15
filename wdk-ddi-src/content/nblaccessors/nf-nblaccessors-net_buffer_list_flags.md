---
UID: NF:nblaccessors.NET_BUFFER_LIST_FLAGS
title: NET_BUFFER_LIST_FLAGS
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: NET_BUFFER_LIST_FLAGS is a macro that NDIS drivers use to get the flags associated with a NET_BUFFER_LIST structure.
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
 - NET_BUFFER_LIST_FLAGS
f1_keywords:
 - NET_BUFFER_LIST_FLAGS
 - nblaccessors/NET_BUFFER_LIST_FLAGS
dev_langs:
 - c++
---


# NET_BUFFER_LIST_FLAGS macro


## -description

**NET_BUFFER_LIST_FLAGS** is a macro that NDIS drivers use to get the flags associated with a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_FLAGS** returns the **Flags** member of the indicated **NET_BUFFER_LIST** structure.

## -remarks

For definitions of possible **NET_BUFFER_LIST** structure flags, see [**NDIS_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md).

## -see-also

[**NDIS_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)
