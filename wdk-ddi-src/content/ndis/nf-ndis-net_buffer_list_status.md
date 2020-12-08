---
UID: NF:ndis.NET_BUFFER_LIST_STATUS
title: NET_BUFFER_LIST_STATUS macro (ndis.h)
description: NET_BUFFER_LIST_STATUS is a macro that NDIS drivers use to access the StatusCode member of a NET_BUFFER_LIST structure.
tech.root: netvista
ms.date: 04/13/2018
keywords: ["NET_BUFFER_LIST_STATUS macro"]
ms.keywords: NET_BUFFER_LIST_STATUS
req.header: ndis.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - NET_BUFFER_LIST_STATUS
 - ndis/NET_BUFFER_LIST_STATUS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NET_BUFFER_LIST_STATUS
---

# NET_BUFFER_LIST_STATUS macro


## -description

**NET_BUFFER_LIST_STATUS** is a macro that NDIS drivers use to access the **StatusCode** member of a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_STATUS** returns the value of the **StatusCode** member of the indicated [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -remarks

Miniport drivers and NDIS intermediate drivers can use **StatusCode** for their own purposes.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)

