---
UID: NF:ndis.NET_BUFFER_CURRENT_MDL
title: NET_BUFFER_CURRENT_MDL macro (ndis.h)
description: NET_BUFFER_CURRENT_MDL is a macro that NDIS drivers use to get the CurrentMdl member of a NET_BUFFER_DATA structure in a NET_BUFFER structure.
tech.root: netvista
ms.assetid: 0413542c-5067-4226-94a7-16d79508f97d
ms.date: 04/12/2018
ms.topic: macro
ms.keywords: NET_BUFFER_CURRENT_MDL
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
- NET_BUFFER_CURRENT_MDL
product:
- Windows
targetos: Windows

---

# NET_BUFFER_CURRENT_MDL macro


## -description

**NET_BUFFER_CURRENT_MDL** is a macro that NDIS drivers use to get the **CurrentMdl** member of a [**NET_BUFFER_DATA**](ns-ndis-_net_buffer_data.md) structure in a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_CURRENT_MDL** returns the value of the **CurrentMdl** member of the indicated [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -remarks

The return value is a pointer to the first MDL that the current driver is using. This pointer provides an optimization that improves performance by skipping over any MDLs that the current driver is not using.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

[**NET_BUFFER_DATA**](ns-ndis-_net_buffer_data.md)
