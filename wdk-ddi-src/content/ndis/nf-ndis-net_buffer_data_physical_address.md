---
UID: NF:ndis.NET_BUFFER_DATA_PHYSICAL_ADDRESS
title: NET_BUFFER_DATA_PHYSICAL_ADDRESS macro (ndis.h)
description: The NET_BUFFER_DATA_PHYSICAL_ADDRESS macro retrieves the DataPhysicalAddress member of a NET_BUFFER structure.
tech.root: netvista
ms.assetid: 116afdd8-6a36-43d0-a8f3-3724d317a758
ms.date: 04/12/2018
keywords: ["NET_BUFFER_DATA_PHYSICAL_ADDRESS macro"]
ms.keywords: NET_BUFFER_DATA_PHYSICAL_ADDRESS
req.header: ndis.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: Supported in NDIS 6.1 and later.
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
 - NET_BUFFER_DATA_PHYSICAL_ADDRESS
 - ndis/NET_BUFFER_DATA_PHYSICAL_ADDRESS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NET_BUFFER_DATA_PHYSICAL_ADDRESS
---

# NET_BUFFER_DATA_PHYSICAL_ADDRESS macro


## -description

The **NET_BUFFER_DATA_PHYSICAL_ADDRESS** macro retrieves the **DataPhysicalAddress** member of a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_DATA_PHYSICAL_ADDRESS** returns the **DataPhysicalAddress** member of a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -remarks

NDIS network drivers should use the **NET_BUFFER_DATA_PHYSICAL_ADDRESS** macro to get the **DataPhysicalAddress** member of a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

