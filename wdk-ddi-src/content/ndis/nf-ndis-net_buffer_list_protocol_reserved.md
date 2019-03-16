---
UID: NF:ndis.NET_BUFFER_LIST_PROTOCOL_RESERVED
title: NET_BUFFER_LIST_PROTOCOL_RESERVED macro (ndis.h)
description: NET_BUFFER_LIST_PROTOCOL_RESERVED is a macro that NDIS drivers use to access the ProtocolReserved member of a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 2d6cc00f-2f22-4105-9e01-7cc179a0b851
ms.date: 04/13/2018
ms.topic: macro
ms.keywords: NET_BUFFER_LIST_PROTOCOL_RESERVED
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
- NET_BUFFER_LIST_PROTOCOL_RESERVED
product:
- Windows
targetos: Windows

---

# NET_BUFFER_LIST_PROTOCOL_RESERVED macro


## -description

**NET_BUFFER_LIST_PROTOCOL_RESERVED** is a macro that NDIS drivers use to access the **ProtocolReserved** member of a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_PROTOCOL_RESERVED** returns a pointer to the start of the **ProtocolReserved** member of the indicated [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -remarks

Protocol drivers and NDIS intermediate drivers can use **ProtocolReserved** for their own purposes.

> [!NOTE]
> Only one driver can use **ProtocolReserved** . Therefore, if another driver has used **ProtocolReserved**, an intermediate driver cannot use it.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
