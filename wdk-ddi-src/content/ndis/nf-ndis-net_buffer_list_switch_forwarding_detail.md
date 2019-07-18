---
UID: NF:ndis.NET_BUFFER_LIST_SWITCH_FORWARDING_DETAIL
title: NET_BUFFER_LIST_SWITCH_FORWARDING_DETAIL macro (ndis.h)
description: Hyper-V extensible switch extensions use the NET_BUFFER_LIST_SWITCH_FORWARDING_DETAIL macro to access the NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO union in the extensible switch context area in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 58680bce-dbd5-43c2-aca8-0e922ef51155
ms.date: 04/13/2018
ms.topic: macro
f1_keywords:
 - "ndis/NET_BUFFER_LIST_SWITCH_FORWARDING_DETAIL"
ms.keywords: NET_BUFFER_LIST_SWITCH_FORWARDING_DETAIL
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
- NET_BUFFER_LIST_SWITCH_FORWARDING_DETAIL
product:
- Windows
targetos: Windows

---

# NET_BUFFER_LIST_SWITCH_FORWARDING_DETAIL macro


## -description

Hyper-V extensible switch extensions use the **NET_BUFFER_LIST_SWITCH_FORWARDING_DETAIL** macro to access the [**NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO**](ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info.md) union in the extensible switch context area in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

The **NET_BUFFER_LIST_SWITCH_FORWARDING_DETAIL** macro returns a pointer to the [**NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO**](ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info.md) union within the specified [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

> [!NOTE]
> **NET_BUFFER_LIST_SWITCH_FORWARDING_DETAIL** returns **NULL** if the [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure does not contain an [**NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO**](ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info.md) structure.

## -remarks

## -see-also

[Adding Extensible Switch Destination Port Data to a Packet](https://docs.microsoft.com/windows-hardware/drivers/network/adding-extensible-switch-destination-port-data-to-a-packet)

[Cloning Packet Traffic](https://docs.microsoft.com/windows-hardware/drivers/network/cloning-or-duplicating-packet-traffic)

[Excluding Packet Delivery to Extensible Switch Destination Ports](https://docs.microsoft.com/windows-hardware/drivers/network/excluding-packet-delivery-to-extensible-switch-destination-ports)

[Forwarding Extensions](https://docs.microsoft.com/windows-hardware/drivers/network/forwarding-extensions)

[Forwarding Packets to Hyper-V Extensible Switch Ports](https://docs.microsoft.com/windows-hardware/drivers/network/forwarding-packets-to-hyper-v-extensible-switch-ports)

[Forwarding Packets to Physical Network Adapters](https://docs.microsoft.com/windows-hardware/drivers/network/forwarding-packets-to-physical-network-adapters)

[Modifying a Packet's Extensible Switch Source Port Data](https://docs.microsoft.com/windows-hardware/drivers/network/modifying-a-packet-s-extensible-switch-source-port-data)

[Overview of the Hyper-V Extensible Switch](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-the-hyper-v-extensible-switch)

[Packet Management Guidelines for the Extensible Switch Data Path](https://docs.microsoft.com/windows-hardware/drivers/network/packet-management-guidelines-for-the-extensible-switch-data-path)

[Querying a Packet's Extensible Switch Source Port Data](https://docs.microsoft.com/windows-hardware/drivers/network/querying-a-packet-s-extensible-switch-source-port-data)

[**NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO**](ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info.md)

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
