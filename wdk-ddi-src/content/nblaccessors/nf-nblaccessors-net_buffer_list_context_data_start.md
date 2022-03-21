---
UID: NF:nblaccessors.NET_BUFFER_LIST_CONTEXT_DATA_START
tech.root: netvista
title: NET_BUFFER_LIST_CONTEXT_DATA_START
ms.date: 03/16/2022
targetos: Windows
description: 
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
req.target-min-winverclnt: WIN11_NEXT
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
 - NET_BUFFER_LIST_CONTEXT_DATA_START
f1_keywords:
 - NET_BUFFER_LIST_CONTEXT_DATA_START
 - nblaccessors/NET_BUFFER_LIST_CONTEXT_DATA_START
dev_langs:
 - c++
helpviewer_keywords:
 - NET_BUFFER_LIST_CONTEXT_DATA_START
---

## -description

**NET_BUFFER_LIST_CONTEXT_DATA_START** is a macro that NDIS drivers use to get a pointer to the [**NET_BUFFER_LIST_CONTEXT**](../nbl/ns-nbl-net_buffer_list_context.md) context space that is associated with a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_CONTEXT_DATA_START** returns a pointer to the **NET_BUFFER_LIST_CONTEXT** context space that is associated with the indicated [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -remarks

**NET_BUFFER_LIST_CONTEXT_DATA_START** returns a pointer to the start of the *used context space* in the **ContextData** member of the [**NET_BUFFER_LIST_CONTEXT**](../nbl/ns-nbl-net_buffer_list_context.md) structure.

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

[**NET_BUFFER_LIST_CONTEXT**](../nbl/ns-nbl-net_buffer_list_context.md)

