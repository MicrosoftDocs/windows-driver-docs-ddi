---
UID: NF:ndis.NET_BUFFER_CURRENT_MDL_OFFSET
title: NET_BUFFER_CURRENT_MDL_OFFSET macro (ndis.h)
description: NET_BUFFER_CURRENT_MDL_OFFSET is a macro that NDIS drivers use to get the CurrentMdlOffset member of a NET_BUFFER structure.
tech.root: netvista
ms.assetid: 0ec50e00-4cb4-4844-9951-441fe7c13f0c
ms.date: 04/12/2018
keywords: ["NET_BUFFER_CURRENT_MDL_OFFSET macro"]
f1_keywords:
 - "ndis/NET_BUFFER_CURRENT_MDL_OFFSET"
 - "NET_BUFFER_CURRENT_MDL_OFFSET"
ms.keywords: NET_BUFFER_CURRENT_MDL_OFFSET
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndis.h
api_name: 
- NET_BUFFER_CURRENT_MDL_OFFSET
targetos: Windows

---

# NET_BUFFER_CURRENT_MDL_OFFSET macro


## -description

**NET_BUFFER_CURRENT_MDL_OFFSET** is a macro that NDIS drivers use to get the **CurrentMdlOffset** member of a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_CURRENT_MDL_OFFSET** returns the value of the **CurrentMdlOffset** member of the indicated [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -remarks

The return value specifies the offset, in bytes, to the beginning of the used data space in the MDL that is specified by the **CurrentMdl** member of the [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)
