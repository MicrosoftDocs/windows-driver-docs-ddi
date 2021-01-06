---
UID: NF:nblaccessors.NET_BUFFER_LIST_PROTOCOL_RESERVED
title: NET_BUFFER_LIST_PROTOCOL_RESERVED
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: NET_BUFFER_LIST_PROTOCOL_RESERVED is a macro that NDIS drivers use to access the ProtocolReserved member of a NET_BUFFER_LIST structure.
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
 - NET_BUFFER_LIST_PROTOCOL_RESERVED
f1_keywords:
 - NET_BUFFER_LIST_PROTOCOL_RESERVED
 - nblaccessors/NET_BUFFER_LIST_PROTOCOL_RESERVED
dev_langs:
 - c++
---


# NET_BUFFER_LIST_PROTOCOL_RESERVED macro


## -description

**NET_BUFFER_LIST_PROTOCOL_RESERVED** is a macro that NDIS drivers use to access the **ProtocolReserved** member of a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_PROTOCOL_RESERVED** returns a pointer to the start of the **ProtocolReserved** member of the indicated [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -remarks

Protocol drivers and NDIS intermediate drivers can use **ProtocolReserved** for their own purposes.

> [!NOTE]
> Only one driver can use **ProtocolReserved** . Therefore, if another driver has used **ProtocolReserved**, an intermediate driver cannot use it.

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)



