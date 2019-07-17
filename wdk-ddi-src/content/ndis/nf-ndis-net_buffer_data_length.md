---
UID: NF:ndis.NET_BUFFER_DATA_LENGTH
title: NET_BUFFER_DATA_LENGTH macro (ndis.h)
description: NET_BUFFER_DATA_LENGTH is a macro that NDIS drivers use to get the amount of used data space in a NET_BUFFER structure.
tech.root: netvista
ms.assetid: becba604-f2cd-49f4-bf64-ec8055047669
ms.date: 04/12/2018
ms.topic: macro
f1_keywords:
 - "ndis/NET_BUFFER_DATA_LENGTH"
ms.keywords: NET_BUFFER_DATA_LENGTH
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
- NET_BUFFER_DATA_LENGTH
product:
- Windows
targetos: Windows

---

# NET_BUFFER_DATA_LENGTH macro


## -description

**NET_BUFFER_DATA_LENGTH** is a macro that NDIS drivers use to get the amount of *used data space* in a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_DATA_LENGTH** returns the amount of *used data space* in a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -remarks

**NET_BUFFER_DATA_LENGTH** gets the return value from the **DataLength** member of the [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)
