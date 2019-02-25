---
UID: NS:netadapteroffload._NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES
title: _NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES structure describes a network interface card (NIC)'s capabilities for large send offload (LSO).
tech.root: netvista
ms.assetid: 73c5e8ec-69ef-4c3d-9864-c728f86b3551
ms.date: 01/17/2019
ms.topic: struct
ms.keywords: _NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES, NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_LSO_CAPABILITIES, 
req.header: netadapteroffload.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_LSO_CAPABILITIES
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	netadapteroffload.h
api_name: 
-	_NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES** structure describes a network interface card (NIC)'s capabilities for large send offload (LSO).

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field IPv4

A flag specifying whether the NIC can segment a large TCP packet on IPv4.
 
### -field IPv6

A flag specifying whether the NIC can segment a large TCP packet on IPv6.
 
### -field MaximumOffloadSize

The maximum bytes of user data that the transport can pass to the NIC driver in a single packet.
 
### -field MinimumSegmentCount
 
The minimum number of segments by which a large TCP packet must be divisible before the transport can offload it to the hardware for segmentation.

### -field EvtAdapterOffloadSetLso

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_LSO*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_lso.md) callback function.

## -remarks

Call [**NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES_INIT**](../netadapteroffload/nf-netadapteroffload-net_adapter_offload_lso_capabilities_init.md) to initialize this structure. An initialized **NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES** structure is passed as a parameter to [**NetAdapterOffloadSetLsoCapabilities**](../netadapteroffload/nf-netadapteroffload-netadapteroffloadsetlsocapabilities.md).

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES_INIT**](../netadapteroffload/nf-netadapteroffload-net_adapter_offload_lso_capabilities_init.md)

[**NetAdapterOffloadSetLsoCapabilities**](../netadapteroffload/nf-netadapteroffload-netadapteroffloadsetlsocapabilities.md)
