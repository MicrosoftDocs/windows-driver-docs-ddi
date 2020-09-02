---
UID: NF:netadapter.NetAdapterPowerOffloadSetArpCapabilities
title: NetAdapterPowerOffloadSetArpCapabilities function (netadapter.h)
author: windows-driver-content
description: The NetAdapterPowerOffloadSetArpCapabilities function sets a net adapter's capabilities for IPv4 ARP low power protocol offload.
tech.root: netvista
ms.assetid: 213f7654-fb2a-4160-b1db-3d36d8e119f2
ms.author: windowsdriverdev
ms.date: 10/22/2019
keywords: ["NetAdapterPowerOffloadSetArpCapabilities function"]
ms.keywords: NetAdapterPowerOffloadSetArpCapabilities
req.header: netadapter.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: netadaptercxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
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
 - NetAdapterPowerOffloadSetArpCapabilities
 - netadapter/NetAdapterPowerOffloadSetArpCapabilities
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetAdapterPowerOffloadSetArpCapabilities
product:
 - Windows
---

# NetAdapterPowerOffloadSetArpCapabilities function


## -description

The **NetAdapterPowerOffloadSetArpCapabilities** function sets a net adapter's capabilities for IPv4 ARP low power protocol offload.

## -parameters

### -param Adapter

A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Capabilities

A pointer to a client driver-allocated and initialized [**NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_power_offload_arp_capabilities.md) structure.

## -returns

This function does not return a value.

## -remarks

Client drivers typically call this function from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this function before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_power_offload_arp_capabilities.md)

[**NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_power_offload_arp_capabilities_init.md)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md)

[**NetAdapterStart**](nf-netadapter-netadapterstart.md)

