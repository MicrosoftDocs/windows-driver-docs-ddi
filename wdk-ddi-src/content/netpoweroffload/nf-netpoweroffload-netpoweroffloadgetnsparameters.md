---
UID: NF:netpoweroffload.NetPowerOffloadGetNSParameters
title: NetPowerOffloadGetNSParameters function (netpoweroffload.h)
author: windows-driver-content
description: The NetPowerOffloadGetNSParameters method gets parameters for an IPv6 Neighbor Solicitation (NS) low power protocol offload to a net adapter.
tech.root: netvista
ms.assetid: 4434a42f-2f3a-4d19-979c-52de51133b44
ms.author: windowsdriverdev
ms.date: 10/03/2019
f1_keywords:
 - "netpoweroffload/NetPowerOffloadGetNSParameters"
ms.keywords: NetPowerOffloadGetNSParameters
req.header: netpoweroffload.h
req.include-header:
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
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetPowerOffloadGetNSParameters
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetPowerOffloadGetNSParameters function


## -description

The **NetPowerOffloadGetNSParameters** method gets parameters for an IPv6 Neighbor Solicitation (NS) low power protocol offload to a net adapter.

## -parameters

### -param PowerOffload

The NETPOWEROFFLOAD object that represents this NS protocol offload.

### -param Parameters

A pointer to a driver-allocated [**NET_POWER_OFFLOAD_NS_PARAMETERS**](../netpoweroffload/ns-netpoweroffload-_net_power_offload_ns_parameters.md) structure that receives the NS parameter information.

## -returns

This method does not return a value.

## -remarks

Call [**NET_POWER_OFFLOAD_NS_PARAMETERS_INIT**](../netpoweroffload/nf-netpoweroffload-net_power_offload_ns_parameters_init.md) to initialize the [**NET_POWER_OFFLOAD_NS_PARAMETERS**](../netpoweroffload/ns-netpoweroffload-_net_power_offload_ns_parameters.md) structure before calling this method.

The client driver must only call **NetPowerOffloadGetNSParameters** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_NS_PARAMETERS**](../netpoweroffload/ns-netpoweroffload-_net_power_offload_ns_parameters.md)

[**NET_POWER_OFFLOAD_NS_PARAMETERS_INIT**](../netpoweroffload/nf-netpoweroffload-net_power_offload_ns_parameters_init.md)
