---
UID: NF:ndis.NdisSetNblFlag
title: NdisSetNblFlag macro (ndis.h)
description: The NdisSetNblFlag macro sets a flag in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: fb399afc-ff20-43aa-9c9c-7be525e61d1f
ms.date: 04/16/2018
ms.topic: macro
f1_keywords:
 - "ndis/NdisSetNblFlag"
ms.keywords: NdisSetNblFlag
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
- NdisSetNblFlag
product:
- Windows
targetos: Windows

---

# NdisSetNblFlag macro


## -description

The **NdisSetNblFlag** macro sets a flag in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _F

The flag in the **NblFlags** member of the **NET_BUFFER_LIST** structure to set.

## -remarks

NDIS drivers use the **NdisSetNblFlag** macro to set the specified flag (*\_F*) in the **NblFlags** member of a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

For more information about the flags, see the **NblFlags** member on the **NET_BUFFER_LIST** topic.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
