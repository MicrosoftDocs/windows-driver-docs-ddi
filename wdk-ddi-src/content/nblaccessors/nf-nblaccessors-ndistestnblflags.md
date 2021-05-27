---
UID: NF:nblaccessors.NdisTestNblFlags
title: NdisTestNblFlags
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NdisTestNblFlags macro tests the setting of a set of flags in a NET_BUFFER_LIST structure.
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
 - NdisTestNblFlags
f1_keywords:
 - NdisTestNblFlags
 - nblaccessors/NdisTestNblFlags
dev_langs:
 - c++
---


# NdisTestNblFlags macro


## -description

The **NdisTestNblFlags** macro tests the setting of a set of flags in a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _F

The flags, combined with a bitwise OR operation, in the **NblFlags** member of the **NET_BUFFER_LIST** structure to test.

## -returns

**NdisTestNblFlags** returns **TRUE** if all flags that are specified in the *\_F* parameter are set. Otherwise, this macro returns **FALSE**.

## -remarks

NDIS drivers use the **NdisTestNblFlags** macro to retrieve the state of the specified flags (*\_F*) in the **NblFlags** member of a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

Use **NdisTestNblFlags** to determine whether a set of specified flags are all set.

For more information about the flags, see the **NblFlags** member on the **NET_BUFFER_LIST** topic.

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)


