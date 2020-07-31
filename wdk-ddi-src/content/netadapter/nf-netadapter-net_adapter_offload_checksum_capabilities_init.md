---
UID: NF:netadapter.NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT
title: NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT function (netadapter.h)
description: The NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT method initializes a NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES structure.
tech.root: netvista
ms.assetid: 22fa6f17-30aa-4ca4-ab53-a3c95591a68f
ms.date: 01/18/2019
keywords: ["NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT function"]
f1_keywords:
 - "netadapter/NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT"
 - "NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT"
ms.keywords: NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib: netadaptercxstub.lib
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
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT
targetos: Windows
ms.custom: 19H1
---

# NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT function


## -description



The **NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT** method initializes a [**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md) structure.

## -parameters

### -param ChecksumCapabilities

A pointer to a driver-allocated [**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md) structure.

### -param IPv4

A flag specifying whether the hardware can calculate and validate IPv4 checksum.

### -param Tcp

A flag specifying whether the hardware can calculate and validate TCP checksum.

### -param Udp

A flag specifying whether the hardware can calculate and validate UDP checksum.

### -param EvtAdapterOffloadSetChecksum

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM*](nc-netadapter-evt_net_adapter_offload_set_checksum.md) callback function.

## -remarks

The [**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md) structure initialized by this method is passed as a parameter to the [**NetAdapterOffloadSetChecksumCapabilities**](nf-netadapter-netadapteroffloadsetchecksumcapabilities.md) method.

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md)
