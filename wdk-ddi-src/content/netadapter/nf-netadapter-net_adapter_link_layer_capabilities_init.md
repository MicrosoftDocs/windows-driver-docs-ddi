---
UID: NF:netadapter.NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT
title: NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT function
description: Initializes the NET_ADAPTER_LINK_LAYER_CAPABILITIES structure.
tech.root: netvista
ms.assetid: f73e2515-c7e3-46f0-b5bd-741c24e65cbd
ms.date: 02/05/2018
ms.topic: function
ms.keywords: NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT** method initializes a [NET_ADAPTER_LINK_LAYER_CAPABILITIES](ns-netadapter-_net_adapter_link_layer_capabilities.md) structure.

## -parameters

### -param LinkLayerCapabilities
A pointer to the driver-allocated [NET_ADAPTER_LINK_LAYER_CAPABILITIES](ns-netadapter-_net_adapter_link_layer_capabilities.md) structure that describes the link layer capabilities of the adapter.

### -param SupportedPacketFilters
An enumeration value of [NET_PACKET_FILTER_TYPES_FLAGS](ne-netadapter-_net_packet_filter_types_flags.md) that specifies packet filters that the adapter supports.

### -param MaxMulticastListSize
The multicast address list size for the adapter.

### -param SupportedStatistics
A bitwise OR of [NET_ADAPTER_STATISTICS_FLAGS](ne-netadapter-_net_adapter_statistics_flags.md)-typed flags specifying statistics the adapter supports.

### -param MaxTxLinkSpeed
The maximum transmit link speed of the adapter in bits per second. For more information, see [OID_GEN_MAX_LINK_SPEED](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-max-link-speed).

### -param MaxRxLinkSpeed
The maximum receive link speed of the adapter in bits per second. For more information, see [OID_GEN_MAX_LINK_SPEED](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-max-link-speed).

## -returns

This method does not return a value.

## -remarks

**NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT** zeroes out the [NET_ADAPTER_LINK_LAYER_CAPABILITIES](ns-netadapter-_net_adapter_link_layer_capabilities.md) structure and then sets all of its members.



### Example

```c++
NET_ADAPTER_LINK_LAYER_CAPABILITIES linkLayerCapabilities;
NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT(
      &linkLayerCapabilities,
      NIC_SUPPORTED_FILTERS,
      NIC_MAX_MCAST_LIST,
      NIC_SUPPORTED_STATISTICS,
      maxXmitLinkSpeed,
      maxRcvLinkSpeed);
```

## -see-also
