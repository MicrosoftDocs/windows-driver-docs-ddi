---
UID: NS:netadapteroffload._NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
title: NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES (netadapteroffload.h)
author: windows-driver-content
description: The NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES structure describes a network interface card (NIC)'s capabilities for receive segment coalescence (RSC).
tech.root: netvista
ms.assetid: ec0a7407-64eb-477e-be2e-ada7c1c3bcc7
ms.author: windowsdriverdev
ms.date: 11/07/2019
keywords: ["NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES structure"]
ms.keywords: NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES, NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES,
req.header: netadapteroffload.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
 - netadapteroffload/_NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
 - NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
 - netadapteroffload/NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapteroffload.h
api_name:
 - NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES
product:
 - Windows
---

# NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES structure


## -description

The **NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES** structure describes a network interface card (NIC)'s capabilities for receive segment coalescence (RSC).

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field IPv4

 
A flag specifying whether the hardware can perform receive segment coalescence (RSC) on IPv4 packets.

### -param IPv6

A flag specifying whether the hardware can perform RSC on IPv6 packets.

### -param Timestamp

A flag specifying whether the hardware can perform RSC on packets with a timestamp.

### -field EvtAdapterOffloadSetRsc

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_RSC*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md) callback function.

## -remarks

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md)

[**NetAdapterOffloadSetRscCapabilities**](../netadapteroffload/nf-netadapteroffload-netadapteroffloadsetrsccapabilities.md)

