---
UID: NF:ndis.NET_BUFFER_NEXT_NB
title: NET_BUFFER_NEXT_NB macro (ndis.h)
description: NET_BUFFER_NEXT_NB is a macro that NDIS drivers use to get a pointer to the next NET_BUFFER structure in a linked list of NET_BUFFER structures.
tech.root: netvista
ms.assetid: 64ae6d10-0c08-42f2-be10-a5141cf3c068
ms.date: 04/13/2018
keywords: ["NET_BUFFER_NEXT_NB macro"]
ms.keywords: NET_BUFFER_NEXT_NB
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
 - NET_BUFFER_NEXT_NB
 - ndis/NET_BUFFER_NEXT_NB
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NET_BUFFER_NEXT_NB
---

# NET_BUFFER_NEXT_NB macro


## -description

**NET_BUFFER_NEXT_NB** is a macro that NDIS drivers use to get a pointer to the next [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure in a linked list of **NET_BUFFER** structures.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_NEXT_NB** returns a pointer to the next [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure in the linked list of **NET_BUFFER** structures, or it returns **NULL** if the end of the linked list is reached.

## -remarks

**NET_BUFFER_NEXT_NB** gets the return value from the **Next** member of the [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

