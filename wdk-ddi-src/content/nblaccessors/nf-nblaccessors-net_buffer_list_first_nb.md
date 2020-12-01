---
UID: NF:nblaccessors.NET_BUFFER_LIST_FIRST_NB
title: NET_BUFFER_LIST_FIRST_NB
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: NET_BUFFER_LIST_FIRST_NB is a macro that NDIS drivers use to get the first NET_BUFFER structure in a NET_BUFFER_LIST structure.
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
 - NET_BUFFER_LIST_FIRST_NB
f1_keywords:
 - NET_BUFFER_LIST_FIRST_NB
 - nblaccessors/NET_BUFFER_LIST_FIRST_NB
dev_langs:
 - c++
---

# NET_BUFFER_LIST_FIRST_NB macro


## -description

**NET_BUFFER_LIST_FIRST_NB** is a macro that NDIS drivers use to get the first [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure in a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_FIRST_NB** returns a pointer to the first **NET_BUFFER** structure in the indicated **NET_BUFFER_LIST** structure.

## -remarks

**NET_BUFFER_LIST_FIRST_NB** gets the return value from the **FirstNetBuffer** member of the [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

