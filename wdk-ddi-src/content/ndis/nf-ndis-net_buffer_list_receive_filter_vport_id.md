---
UID: NF:ndis.NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID
title: NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID macro (ndis.h)
description: The NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID macro sets or gets the identifier of a virtual port (VPort) within the out-of-band (OOB) data in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 6ed1f2da-6e14-438e-9f3b-af8d1fbeeec4
ms.date: 04/13/2018
ms.topic: macro
ms.keywords: NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID
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
- NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID
product:
- Windows
targetos: Windows

---

# NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID macro


## -description

The **NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID** macro sets or gets the identifier of a virtual port (VPort) within the out-of-band (OOB) data in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID** returns a USHORT value for a VPort identifier.

## -remarks

Miniport drivers that support the single root I/O virtualization (SR-IOV) interface can use the **NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID** macro to set or get the VPort identifier in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure. The **NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID** macro accesses the VPort identifier from the **VPortId** member of the [**NDIS_NET_BUFFER_LIST_FILTERING_INFO**](ns-ndis-_ndis_net_buffer_list_filtering_info.md) structure.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)

[**NDIS_NET_BUFFER_LIST_FILTERING_INFO**](ns-ndis-_ndis_net_buffer_list_filtering_info.md)
