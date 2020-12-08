---
UID: NF:ndis.NdisTestNblFlags
title: NdisTestNblFlags macro (ndis.h)
description: The NdisTestNblFlags macro tests the setting of a set of flags in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.date: 04/16/2018
keywords: ["NdisTestNblFlags macro"]
ms.keywords: NdisTestNblFlags
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
targetos: Windows
f1_keywords:
 - NdisTestNblFlags
 - ndis/NdisTestNblFlags
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisTestNblFlags
---

# NdisTestNblFlags macro


## -description

The **NdisTestNblFlags** macro tests the setting of a set of flags in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _F

The flags, combined with a bitwise OR operation, in the **NblFlags** member of the **NET_BUFFER_LIST** structure to test.

## -returns

**NdisTestNblFlags** returns **TRUE** if all flags that are specified in the *\_F* parameter are set. Otherwise, this macro returns **FALSE**.

## -remarks

NDIS drivers use the **NdisTestNblFlags** macro to retrieve the state of the specified flags (*\_F*) in the **NblFlags** member of a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

Use **NdisTestNblFlags** to determine whether a set of specified flags are all set.

For more information about the flags, see the **NblFlags** member on the **NET_BUFFER_LIST** topic.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)

