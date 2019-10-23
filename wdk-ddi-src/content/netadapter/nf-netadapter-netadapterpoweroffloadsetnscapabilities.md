---
UID: NF:netadapter.NetAdapterPowerOffloadSetNSCapabilities
title: NetAdapterPowerOffloadSetNSCapabilities function (netadapter.h)
author: windows-driver-content
description: TBD
tech.root:
ms.assetid: 7ee49626-79b4-46e3-a98f-0b9990cb4a2d
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
f1_keywords:
 - "netadapter/NetAdapterPowerOffloadSetNSCapabilities"
ms.keywords: NetAdapterPowerOffloadSetNSCapabilities
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
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
- 
api_location: 
- 
api_name: 
- NetAdapterPowerOffloadSetNSCapabilities
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetAdapterPowerOffloadSetNSCapabilities function


## -description

The **NetAdapterPowerOffloadSetNsCapabilities** method sets a net adapter's capabilities for IPv6 Neighbor Solicitation (NS) low power protocol offload.

## -parameters

### -param Adapter

A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Capabilities

A pointer to a client driver-allocated and initialized [**NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_power_offload_ns_capabilities.md).

## -returns

This method does not return a value.

## -remarks

Client drivers typically call this method from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this method before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_power_offload_ns_capabilities.md)

[**NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_power_offload_ns_capabilities_init.md)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md)

[**NetAdapterStart**](nf-netadapter-netadapterstart.md)