---
UID: NF:ndis.NET_BUFFER_LIST_COALESCED_SEG_COUNT
title: NET_BUFFER_LIST_COALESCED_SEG_COUNT macro (ndis.h)
description: The NET_BUFFER_LIST_COALESCED_SEG_COUNT is a macro that NDIS drivers use to get and set the number of coalesced segments in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 14659885-72c9-4050-bfa4-cd94328c294e
ms.date: 04/12/2018
ms.topic: macro
ms.keywords: NET_BUFFER_LIST_COALESCED_SEG_COUNT
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
- NET_BUFFER_LIST_COALESCED_SEG_COUNT
product:
- Windows
targetos: Windows

---

# NET_BUFFER_LIST_COALESCED_SEG_COUNT macro


## -description

The **NET_BUFFER_LIST_COALESCED_SEG_COUNT** is a macro that NDIS drivers use to get and set the number of coalesced segments in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_COALESCED_SEG_COUNT** returns the **CoalescedSegCount** member of the [**NDIS_RSC_NBL_INFO**](ns-ndis-_ndis_rsc_nbl_info.md) union that is associated with the **TcpRecvSegCoalesceInfo** identifier. The information is retrieved from the **NetBufferListInfo** member of the indicated [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -remarks

This macro uses the [NET_BUFFER_LIST_INFO](nf-ndis-net_buffer_list_info.md) macro to access the **TcpRecvSegCoalesceInfo** information.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)

[**NDIS_RSC_NBL_INFO**](ns-ndis-_ndis_rsc_nbl_info.md)

[NET_BUFFER_LIST_INFO](nf-ndis-net_buffer_list_info.md)
