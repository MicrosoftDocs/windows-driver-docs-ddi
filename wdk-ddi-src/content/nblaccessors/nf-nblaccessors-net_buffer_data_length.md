---
UID: NF:nblaccessors.NET_BUFFER_DATA_LENGTH
title: NET_BUFFER_DATA_LENGTH
ms.date: 10/02/2023
targetos: Windows
description: NET_BUFFER_DATA_LENGTH is a macro that NDIS drivers use to get the amount of used data space in a NET_BUFFER structure.
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
returns-override: true
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nblaccessors.h
api_name:
 - NET_BUFFER_DATA_LENGTH
f1_keywords:
 - NET_BUFFER_DATA_LENGTH
 - nblaccessors/NET_BUFFER_DATA_LENGTH
dev_langs:
 - c++
---

# NET_BUFFER_DATA_LENGTH macro


## -description

**NET_BUFFER_DATA_LENGTH** is a macro that NDIS drivers use to get the amount of *used data space* in a [**NET_BUFFER**](../nbl/ns-nbl-net_buffer.md) structure.

## -syntax

```cpp
#define NET_BUFFER_DATA_LENGTH(_NB) ((_NB)->DataLength)
```

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_DATA_LENGTH** returns the amount of *used data space* in a [**NET_BUFFER**](../nbl/ns-nbl-net_buffer.md) structure.

## -remarks

**NET_BUFFER_DATA_LENGTH** gets the return value from the **DataLength** member of the [**NET_BUFFER**](../nbl/ns-nbl-net_buffer.md) structure.

## -see-also

[**NET_BUFFER**](../nbl/ns-nbl-net_buffer.md)
