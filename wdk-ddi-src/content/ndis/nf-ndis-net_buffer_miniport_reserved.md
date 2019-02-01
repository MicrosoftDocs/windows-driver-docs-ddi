---
UID: NF:ndis.NET_BUFFER_MINIPORT_RESERVED
title: NET_BUFFER_MINIPORT_RESERVED macro (ndis.h)
description: NET_BUFFER_MINIPORT_RESERVED is a macro that NDIS drivers use to access the MiniportReserved member of a NET_BUFFER structure.
tech.root: netvista
ms.assetid: 584b901d-9e3c-4bdc-a5b6-5f0670de6c1e
ms.date: 04/13/2018
ms.topic: macro
ms.keywords: NET_BUFFER_MINIPORT_RESERVED
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
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ndis.h
api_name: 
-	NET_BUFFER_MINIPORT_RESERVED
product:
-	Windows
targetos: Windows

---

# NET_BUFFER_MINIPORT_RESERVED macro


## -description

**NET_BUFFER_MINIPORT_RESERVED** is a macro that NDIS drivers use to access the **MiniportReserved** member of a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_MINIPORT_RESERVED** returns a pointer to the start of the **MiniportReserved** member of the specified [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -remarks

Miniport drivers and NDIS intermediate drivers can use **MiniportReserved** for their own purposes. Miniport drivers typically use **MiniportReserved** to maintain [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure context information for outstanding transfers.

> [!NOTE]
> Only one driver can use **MiniportReserved**. Therefore, if another driver has used **MiniportReserved**, an intermediate driver cannot use it.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)
