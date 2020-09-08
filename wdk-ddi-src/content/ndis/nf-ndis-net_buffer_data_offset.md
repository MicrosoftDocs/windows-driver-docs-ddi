---
UID: NF:ndis.NET_BUFFER_DATA_OFFSET
title: NET_BUFFER_DATA_OFFSET macro (ndis.h)
description: NET_BUFFER_DATA_OFFSET is a macro that NDIS drivers use to get the current offset from the beginning of the data space to the start of the used data space in a NET_BUFFER structure.
tech.root: netvista
ms.assetid: 8de2a456-0b0e-47f1-895b-eee5de319283
ms.date: 04/12/2018
keywords: ["NET_BUFFER_DATA_OFFSET macro"]
ms.keywords: NET_BUFFER_DATA_OFFSET
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
 - NET_BUFFER_DATA_OFFSET
 - ndis/NET_BUFFER_DATA_OFFSET
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NET_BUFFER_DATA_OFFSET
---

# NET_BUFFER_DATA_OFFSET macro


## -description

**NET_BUFFER_DATA_OFFSET** is a macro that NDIS drivers use to get the current offset from the beginning of the data space to the start of the *used data space* in a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_DATA_OFFSET** returns the offset, in bytes, from the beginning of the data space to the start of the *used data space* of the indicated **NET_BUFFER** structure. This value also represents the size of the *unused data space* (available backfill).

## -remarks

**NET_BUFFER_DATA_OFFSET** gets the return value from the **DataOffset** member of the [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

