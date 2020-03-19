---
UID: NF:netadapteroffload.NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT
title: NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT function (netadapteroffload.h)
author: windows-driver-content
description: The NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT method initializes a NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES structure.
tech.root: netvista
ms.assetid: 1df09a2f-d816-407a-8759-142f569f0f57
ms.author: windowsdriverdev
ms.date: 11/07/2019
keywords: ["NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT function"]
f1_keywords:
 - "netadapteroffload/NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT"
ms.keywords: NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT
req.header: netadapteroffload.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level as long as target memory is resident
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
- netadapteroffload.h
api_name: 
- NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT function


## -description

The **NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT** method initializes a [**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md) structure.

## -parameters

### -param RscCapabilities

A pointer to a driver-allocated [**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md) structure.

### -param IPv4

A flag specifying whether the hardware can perform receive segment coalescence (RSC) on IPv4 packets.

### -param IPv6

A flag specifying whether the hardware can perform RSC on IPv6 packets.

### -param Timestamp

A flag specifying whether the hardware can perform RSC on packets with a timestamp.

### -param EvtAdapterOffloadSetRsc

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_RSC*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md) callback function.

## -returns

This method does not return a value.

## -remarks

The [**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md) structure initialized by this method is passed as a parameter to the [**NetAdapterOffloadSetRscCapabilities**](../netadapteroffload/nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md) method.

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md)

[**NetAdapterOffloadSetRscCapabilities**](../netadapteroffload/nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md)
