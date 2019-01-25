---
UID: NF:ndis.NET_BUFFER_LIST_STATUS
title: NET_BUFFER_LIST_STATUS macro (ndis.h)
description: NET_BUFFER_LIST_STATUS is a macro that NDIS drivers use to access the StatusCode member of a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: ae7575c9-785c-4766-80b9-43c31f34fdaa
ms.date: 04/13/2018
ms.topic: macro
ms.keywords: NET_BUFFER_LIST_STATUS
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
-	NET_BUFFER_LIST_STATUS
product:
-	Windows
targetos: Windows

---

# NET_BUFFER_LIST_STATUS macro


## -description

**NET_BUFFER_LIST_STATUS** is a macro that NDIS drivers use to access the **StatusCode** member of a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_STATUS** returns the value of the **StatusCode** member of the indicated [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -remarks

Miniport drivers and NDIS intermediate drivers can use **StatusCode** for their own purposes.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
