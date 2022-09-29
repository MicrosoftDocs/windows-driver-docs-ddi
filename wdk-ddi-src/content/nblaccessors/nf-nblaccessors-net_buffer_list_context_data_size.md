---
UID: NF:nblaccessors.NET_BUFFER_LIST_CONTEXT_DATA_SIZE
tech.root: netvista
title: NET_BUFFER_LIST_CONTEXT_DATA_SIZE
ms.date: 03/16/2022
targetos: Windows
description: NET_BUFFER_LIST_CONTEXT_DATA_SIZE is a macro that NDIS drivers use to get the size of the NET_BUFFER_LIST_CONTEXT data buffer that is associated with a NET_BUFFER_LIST structure.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: nblaccessors.h
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
req.target-type: 
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
 - NET_BUFFER_LIST_CONTEXT_DATA_SIZE
f1_keywords:
 - NET_BUFFER_LIST_CONTEXT_DATA_SIZE
 - nblaccessors/NET_BUFFER_LIST_CONTEXT_DATA_SIZE
dev_langs:
 - c++
helpviewer_keywords:
 - NET_BUFFER_LIST_CONTEXT_DATA_SIZE
---

## -description

**NET_BUFFER_LIST_CONTEXT_DATA_SIZE** is a macro that NDIS drivers use to get the size of the [**NET_BUFFER_LIST_CONTEXT**](../nbl/ns-nbl-net_buffer_list_context.md) data buffer that is associated with a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_CONTEXT_DATA_SIZE** returns the size, in bytes, of the **NET_BUFFER_LIST_CONTEXT** data buffer that is associated with the indicated [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -remarks

**NET_BUFFER_LIST_CONTEXT_DATA_SIZE** gets the return value from the **Size** member of the first [**NET_BUFFER_LIST_CONTEXT**](../nbl/ns-nbl-net_buffer_list_context.md) structure.

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

[**NET_BUFFER_LIST_CONTEXT**](../nbl/ns-nbl-net_buffer_list_context.md)
