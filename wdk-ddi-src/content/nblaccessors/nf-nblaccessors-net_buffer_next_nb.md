---
UID: NF:nblaccessors.NET_BUFFER_NEXT_NB
title: NET_BUFFER_NEXT_NB
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: NET_BUFFER_NEXT_NB is a macro that NDIS drivers use to get a pointer to the next NET_BUFFER structure in a linked list of NET_BUFFER structures.
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
 - NET_BUFFER_NEXT_NB
f1_keywords:
 - NET_BUFFER_NEXT_NB
 - nblaccessors/NET_BUFFER_NEXT_NB
dev_langs:
 - c++
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
