---
UID: NS:netadapter._NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES
title: NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES (netadapter.h)
author: windows-driver-content
description: The NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES structure describes a net adapter's capabilities for IPv6 Neighbor Solicitation (NS) low power protocol offload.
tech.root: netvista
ms.assetid: f740c2ac-25b0-4d04-a524-e5670b53e903
ms.author: windowsdriverdev
ms.date: 10/22/2019
ms.topic: struct
f1_keywords:
 - "netadapter/NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES"
ms.keywords: NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES, NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES, 
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - netadapter.h
api_name: 
 - NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES structure

## -description

The **NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES** structure describes a net adapter's capabilities for IPv6 Neighbor Solicitation (NS) low power protocol offload.

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field NSOffload

A boolean value that specifies if this net adapter supports IPv6 NS protocol offload.
 
### -field MaximumOffloadCount
 
The maximum number of NS protocol offloads that the hardware supports.

## -remarks

Call [**NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_power_offload_ns_capabilities_init.md) to initialize this structure, then call [**NetAdapterPowerOffloadSetNsCapabilities**](../netadapter/nf-netadapter-netadapterpoweroffloadsetnscapabilities.md) to set the net adapter's NS protocol offload capabilities. Client drivers typically call **NetAdapterPowerOffloadSetNsCapabilities** when starting a net adapter, but before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_power_offload_ns_capabilities_init.md)

[**NetAdapterPowerOffloadSetNsCapabilities**](../netadapter/nf-netadapter-netadapterpoweroffloadsetnscapabilities.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)