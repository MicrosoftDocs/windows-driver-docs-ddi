---
UID: NF:netpoweroffload.NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT
title: NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT function (netpoweroffload.h)
author: windows-driver-content
description: The NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT method initializes a NET_POWER_OFFLOAD_ARP_PARAMETERS structure.
tech.root: netvista
ms.assetid: 1d8aa902-5b9e-4975-a0c7-829c6f27af0e
ms.author: windowsdriverdev
ms.date: 09/30/2019
keywords: ["NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT function"]
f1_keywords:
 - "netpoweroffload/NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT"
 - "NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT"
ms.keywords: NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT
req.header: netpoweroffload.h
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
- netpoweroffload.h
api_name: 
- NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT function


## -description

The **NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT** method initializes a [**NET_POWER_OFFLOAD_ARP_PARAMETERS**](../netpoweroffload/ns-netpoweroffload-_net_power_offload_arp_parameters.md) structure.

## -parameters

### -param Parameters

A pointer to a client driver-allocated [**NET_POWER_OFFLOAD_ARP_PARAMETERS**](../netpoweroffload/ns-netpoweroffload-_net_power_offload_arp_parameters.md) structure.

## -returns

This method does not return a value.

## -remarks

This method zeroes out the memory of the **NET_POWER_OFFLOAD_ARP_PARAMETERS** structure, then fills in the **Size** member. Client drivers must then call [**NetPowerOffloadGetArpParameters**](../netpoweroffload/nf-netpoweroffload-netpoweroffloadgetarpparameters.md) to fill in the remaining members of the structure.

The client driver must only call **NET_POWER_OFFLOAD_ARP_PARAMETERS_INIT** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_ARP_PARAMETERS**](../netpoweroffload/ns-netpoweroffload-_net_power_offload_arp_parameters.md)
