---
UID: NF:ndis.NdisClearNblFlag
title: NdisClearNblFlag macro
author: windows-driver-content
description: The NdisClearNblFlag macro clears a flag in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 244839a5-cdc2-4b05-8a96-37c477313238
ms.author: windowsdriverdev
ms.date: 04/16/2018
ms.topic: macro
ms.keywords: NdisClearNblFlag
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
-	NdisClearNblFlag
product:
-	Windows
targetos: Windows

---

# NdisClearNblFlag macro


## -description

The **NdisClearNblFlag** macro clears a flag in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _F

The flag in the **NblFlags** member of the **NET_BUFFER_LIST** structure to clear.

## -returns

This macro does not return a value.

## -remarks

NDIS drivers use the **NdisClearNblFlag** macro to clear the specified flag (*\_F*) in the **NblFlags** member of a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

For more information about the flags, see the **NblFlags** member on the **NET_BUFFER_LIST** topic.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
