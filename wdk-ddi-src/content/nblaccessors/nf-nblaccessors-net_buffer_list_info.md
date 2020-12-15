---
UID: NF:nblaccessors.NET_BUFFER_LIST_INFO
title: NET_BUFFER_LIST_INFO
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: NET_BUFFER_LIST_INFO is a macro that NDIS drivers use to get and set information that applies to all the NET_BUFFER structures in a NET_BUFFER_LIST structure.
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
 - NET_BUFFER_LIST_INFO
f1_keywords:
 - NET_BUFFER_LIST_INFO
 - nblaccessors/NET_BUFFER_LIST_INFO
dev_langs:
 - c++
---

# NET_BUFFER_LIST_INFO macro


## -description

**NET_BUFFER_LIST_INFO** is a macro that NDIS drivers use to get and set information that applies to all the [**NET_BUFFER**](ns-ndis-_net_buffer.md) structures in a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _Id

An ID that indicates the type of information to access from the **NetBufferListInfo** member of the **NET_BUFFER_LIST** structure that the *\_NBL* parameter specifies.

## -returns

**NET_BUFFER_LIST_INFO** returns the information that is associated with the specified ID. The information is retrieved from the **NetBufferListInfo** member of the indicated **NET_BUFFER_LIST** structure.

## -remarks

For a list of the valid **NetBufferListInfo** IDs, see the [**NDIS_NET_BUFFER_LIST_INFO**](ne-ndis-_ndis_net_buffer_list_info.md) enumeration reference page.

The following example demonstrates getting a **NetBufferListInfo** value:

```C++
value = NET_BUFFER_LIST_INFO(pNBL, Id);
```

The following example demonstrates setting a **NetBufferListInfo** value:

```C++
NET_BUFFER_LIST_INFO(pNBL, Id) = value;
```

## -see-also

[**NDIS_NET_BUFFER_LIST_INFO**](ne-ndis-_ndis_net_buffer_list_info.md)

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

