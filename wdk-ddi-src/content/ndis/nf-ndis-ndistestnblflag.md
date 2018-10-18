---
UID: NF:ndis.NdisTestNblFlag
title: NdisTestNblFlag macro
author: windows-driver-content
description: The NdisTestNblFlag macro retrieves the current setting of a flag in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 39001bdc-f751-4c77-983c-3495efd46c87
ms.date: 04/16/2018
ms.topic: macro
ms.keywords: NdisTestNblFlag
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
-	NdisTestNblFlag
product:
-	Windows
targetos: Windows

---

# NdisTestNblFlag macro


## -description

The **NdisTestNblFlag** macro retrieves the current setting of a flag in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _F

The flag in the **NblFlags** member of the **NET_BUFFER_LIST** structure for which to retrieve the current setting.

## -returns

**NdisTestNblFlag** returns **TRUE** if the flag that is specified in the *\_F* parameter is set. Otherwise, this macro returns **FALSE**.

## -remarks

NDIS drivers use the **NdisTestNblFlag** macro to retrieve the setting of the specified flag (*\_F*) in the **NblFlags** member of a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

For more information about the flags, see the **NblFlags** member on the **NET_BUFFER_LIST** topic.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
