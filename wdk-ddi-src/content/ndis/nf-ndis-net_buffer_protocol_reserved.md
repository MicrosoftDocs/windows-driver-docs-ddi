---
UID: NF:ndis.NET_BUFFER_PROTOCOL_RESERVED
title: NET_BUFFER_PROTOCOL_RESERVED macro (ndis.h)
description: NET_BUFFER_PROTOCOL_RESERVED is a macro that NDIS drivers use to get the ProtocolReserved member of a NET_BUFFER structure.
tech.root: netvista
ms.assetid: 8cfd161c-6f2f-4b31-ae49-b570b3d306d6
ms.date: 04/13/2018
keywords: ["NET_BUFFER_PROTOCOL_RESERVED macro"]
f1_keywords:
 - "ndis/NET_BUFFER_PROTOCOL_RESERVED"
 - "NET_BUFFER_PROTOCOL_RESERVED"
ms.keywords: NET_BUFFER_PROTOCOL_RESERVED
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
- NET_BUFFER_PROTOCOL_RESERVED
targetos: Windows

---

# NET_BUFFER_PROTOCOL_RESERVED macro


## -description

**NET_BUFFER_PROTOCOL_RESERVED** is a macro that NDIS drivers use to get the **ProtocolReserved** member of a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_PROTOCOL_RESERVED** returns the value of the **ProtocolReserved** member of the specified [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -remarks

Protocol drivers and NDIS intermediate drivers can use this area for their own purposes. Protocol drivers typically use **ProtocolReserved** to maintain [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure context information for outstanding transfers.

> [!NOTE]
> Only one driver can use **ProtocolReserved**. Therefore, if an another driver has used **ProtocolReserved**, an intermediate driver cannot use it.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)
