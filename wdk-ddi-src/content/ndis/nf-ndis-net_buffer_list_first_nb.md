---
UID: NF:ndis.NET_BUFFER_LIST_FIRST_NB
title: NET_BUFFER_LIST_FIRST_NB macro
author: windows-driver-content
description: NET_BUFFER_LIST_FIRST_NB is a macro that NDIS drivers use to get the first NET_BUFFER structure in a NET_BUFFER_LIST structure.
ms.assetid: 907baec2-ceec-40e7-b372-9771ffd160bc
ms.author: windowsdriverdev
ms.date: 04/12/2018
ms.topic: macro
ms.keywords: NET_BUFFER_LIST_FIRST_NB
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
-	NET_BUFFER_LIST_FIRST_NB
product: Windows
targetos: Windows

---

# NET_BUFFER_LIST_FIRST_NB macro


## -description

**NET_BUFFER_LIST_FIRST_NB** is a macro that NDIS drivers use to get the first [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_FIRST_NB** returns a pointer to the first **NET_BUFFER** structure in the indicated **NET_BUFFER_LIST** structure.

## -remarks

**NET_BUFFER_LIST_FIRST_NB** gets the return value from the **FirstNetBuffer** member of the [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)