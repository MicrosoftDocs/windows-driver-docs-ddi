---
UID: NF:netadapter.NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT
title: NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT function (netadapter.h)
author: windows-driver-content
description: The NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT method initializes a NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES structure.
tech.root: netvista
ms.assetid: c7a01b5d-7ad6-498e-bd6a-0d66eb9bd220
ms.author: windowsdriverdev
ms.date: 10/22/2019
keywords: ["NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT function"]
ms.keywords: NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT
req.header: netadapter.h
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT
 - netadapter/NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT
product:
 - Windows
---

# NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT function


## -description

The **NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT** method initializes a [**NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_power_offload_arp_capabilities.md) structure.

## -parameters

### -param Capabilities

A pointer to a client driver-allocated [**NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_power_offload_arp_capabilities.md) structure.

### -param MaximumOffloadCount

The maximum number of ARP protocol offloads that the hardware supports.

## -returns

This method does not return a value.

## -remarks

After calling this method to initialize the **NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES** structure, call [**NetAdapterPowerOffloadSetArpCapabilities**](../netadapter/nf-netadapter-netadapterpoweroffloadsetarpcapabilities.md) to set the net adapter's ARP protocol offload capabilities. Client drivers typically call **NetAdapterPowerOffloadSetArpCapabilities** when starting a net adapter, but before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_power_offload_arp_capabilities.md)

[**NetAdapterPowerOffloadSetArpCapabilities**](../netadapter/nf-netadapter-netadapterpoweroffloadsetarpcapabilities.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)

