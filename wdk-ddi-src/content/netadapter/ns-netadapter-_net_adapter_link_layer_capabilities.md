---
UID: NS:netadapter._NET_ADAPTER_LINK_LAYER_CAPABILITIES
title: _NET_ADAPTER_LINK_LAYER_CAPABILITIES
author: windows-driver-content
description: Describes the link layer capabilities of the adapter.
tech.root: netvista
ms.assetid: 24888f71-0e12-41c8-a218-9289b1f5b288
ms.author: windowsdriverdev
ms.date: 02/06/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_ADAPTER_LINK_LAYER_CAPABILITIES, *PNET_ADAPTER_LINK_LAYER_CAPABILITIES, NET_ADAPTER_LINK_LAYER_CAPABILITIES, 
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_LINK_LAYER_CAPABILITIES, *PNET_ADAPTER_LINK_LAYER_CAPABILITIES
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_LINK_LAYER_CAPABILITIES
product:
-	Windows
targetos: Windows
product:
- Windows
---

# _NET_ADAPTER_LINK_LAYER_CAPABILITIES structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Describes the link layer capabilities of the adapter.

## -struct-fields

### -field Size
The size of this structure, in bytes.
 
### -field SupportedPacketFilters
Indicates the packet filters that the adapter supports. This value is a bitwise OR of [NET_PACKET_FILTER_TYPES_FLAGS](ne-netadapter-_net_packet_filter_types_flags.md)-typed flags.
 
### -field MaxMulticastListSize
The multicast address list size for the adapter.
 
### -field SupportedStatistics
The statistics that the adapter supports. This value is a bitwise OR of [NET_ADAPTER_STATISTICS_FLAGS](ne-netadapter-_net_adapter_statistics_flags.md)-typed flags.
 
### -field MaxTxLinkSpeed
The maximum transmit link speed of the adapter in bits per second. For more information, see [OID_GEN_MAX_LINK_SPEED](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-max-link-speed).
 
### -field MaxRxLinkSpeed
 The maximum receive link speed of the adapter in bits per second. For more information, see [OID_GEN_MAX_LINK_SPEED](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-max-link-speed).

## -remarks
The client driver passes an initialized **NET_ADAPTER_LINK_LAYER_CAPABILITIES** structure as an input parameter value to [NetAdapterSetLinkLayerCapabilities](nf-netadapter-netadaptersetlinklayercapabilities.md).

Call [NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT](nf-netadapter-net_adapter_link_layer_capabilities_init.md) to initialize this structure.



## -see-also
