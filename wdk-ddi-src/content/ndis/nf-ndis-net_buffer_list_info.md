---
UID: NF:ndis.NET_BUFFER_LIST_INFO
title: NET_BUFFER_LIST_INFO macro
author: windows-driver-content
description: NET_BUFFER_LIST_INFO is a macro that NDIS drivers use to get and set information that applies to all the NET_BUFFER structures in a NET_BUFFER_LIST structure.
ms.assetid: 2d4727fc-43bf-41a5-8e2e-3c5de814aaef
ms.author: windowsdriverdev
ms.date: 04/12/2018
ms.topic: macro
ms.keywords: NET_BUFFER_LIST_INFO
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
-	NET_BUFFER_LIST_INFO
product: Windows
targetos: Windows

---

# NET_BUFFER_LIST_INFO macro


## -description

**NET_BUFFER_LIST_INFO** is a macro that NDIS drivers use to get and set information that applies to all the [**NET_BUFFER**](ns-ndis-_net_buffer.md) structures in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

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

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)