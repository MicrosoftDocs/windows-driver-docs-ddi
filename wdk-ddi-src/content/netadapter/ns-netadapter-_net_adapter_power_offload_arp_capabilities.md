---
UID: NS:netadapter._NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES
title: NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES (netadapter.h)
description: The NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES structure describes a net adapter's capabilities for IPv4 ARP low power protocol offload.
tech.root: netvista
ms.date: 10/21/2019
keywords: ["NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES structure"]
ms.keywords: NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES, NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES,
req.header: netadapter.h
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
req.typenames: NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES
 - netadapter/_NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES
 - NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES
 - netadapter/NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES
product:
 - Windows
---

# NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES structure


## -description

The **NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES** structure describes a net adapter's capabilities for IPv4 ARP low power protocol offload.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field ArpOffload

A boolean value that specifies if this net adapter supports IPv4 ARP protocol offload.

### -field MaximumOffloadCount

 
The maximum number of ARP protocol offloads that the hardware supports.

## -remarks

Call [**NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_power_offload_arp_capabilities_init.md) to initialize this structure, then call [**NetAdapterPowerOffloadSetArpCapabilities**](../netadapter/nf-netadapter-netadapterpoweroffloadsetarpcapabilities.md) to set the net adapter's ARP protocol offload capabilities. Client drivers typically call **NetAdapterPowerOffloadSetArpCapabilities** when starting a net adapter, but before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_power_offload_arp_capabilities_init.md)

[**NetAdapterPowerOffloadSetArpCapabilities**](../netadapter/nf-netadapter-netadapterpoweroffloadsetarpcapabilities.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)
