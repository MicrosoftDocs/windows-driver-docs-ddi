---
UID: NF:nblaccessors.NdisClearNblFlag
title: NdisClearNblFlag
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NdisClearNblFlag macro clears a flag in a NET_BUFFER_LIST structure.
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
 - NdisClearNblFlag
f1_keywords:
 - NdisClearNblFlag
 - nblaccessors/NdisClearNblFlag
dev_langs:
 - c++
---


# NdisClearNblFlag macro


## -description

The **NdisClearNblFlag** macro clears a flag in a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _F

The flag in the **NblFlags** member of the **NET_BUFFER_LIST** structure to clear.

## -remarks

NDIS drivers use the **NdisClearNblFlag** macro to clear the specified flag (*\_F*) in the **NblFlags** member of a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

For more information about the flags, see the **NblFlags** member on the **NET_BUFFER_LIST** topic.

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)
