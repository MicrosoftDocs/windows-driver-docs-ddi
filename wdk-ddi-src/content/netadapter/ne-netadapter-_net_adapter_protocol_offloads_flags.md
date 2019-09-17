---
UID: NE:netadapter._NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS
title: _NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS (netadapter.h)
description: Specifies the low power protocol offload capabilities of a network adapter.
tech.root: netvista
ms.assetid: 06a56aed-bad4-499c-adb6-3aa677ea2e88
ms.date: 02/05/2018
ms.topic: enum
f1_keywords:
 - "netadapter/NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS"
ms.keywords: _NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS, NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS
targetos: Windows
product:
- Windows
---

# _NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS enumeration

## -description



Specifies the low power protocol offload capabilities of a network adapter.

## -enum-fields

### -field NET_ADAPTER_PROTOCOL_OFFLOAD_ARP : 
If this bit is set, the overlying driver will request the network adapter to enable the ARP protocol offload capability. As soon as this protocol offload has been configured by a set request of [OID_PM_ADD_PROTOCOL_OFFLOAD](https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-add-protocol-offload), the driver should enable the network adapter to respond to IPv4 ARP packets while it is in a low-power state.

### -field NET_ADAPTER_PROTOCOL_OFFLOAD_NS : 
If this bit is set, the overlying driver will request the network adapter to enable the IPv6 Neighbor Solicitation (NS) protocol offload capability. As soon as this protocol offload has been configured by a set request of [OID_PM_ADD_PROTOCOL_OFFLOAD](https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-add-protocol-offload), the driver should enable the network adapter to respond to NS packets while it is in a low-power state.

### -field NET_ADAPTER_PROTOCOL_OFFLOAD_80211_RSN_REKEY : 
If this bit is set, the overlying driver will request the network adapter to enable the IEEE 802.11i Robust Security Network (RSN) protocol offload capability. As soon as this protocol offload has been configured by a set request of [OID_PM_ADD_PROTOCOL_OFFLOAD](https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-add-protocol-offload), the driver should enable the network adapter to respond to RSN re-key requests packets while it is in a low power state.

## -remarks

The **NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS** enumeration is used to specify protocol offload capabilities in the [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure.

The client driver passes an initialized **NET_ADAPTER_POWER_CAPABILITIES** structure as an input parameter value to [NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md).



## -see-also

[NDIS_PM_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_pm_parameters.md)
