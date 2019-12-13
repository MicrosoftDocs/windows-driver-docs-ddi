---
UID: NF:netpoweroffloadlist.NET_POWER_OFFLOAD_LIST_INIT
title: NET_POWER_OFFLOAD_LIST_INIT function (netpoweroffloadlist.h)
author: windows-driver-content
description: The NET_POWER_OFFLOAD_LIST_INIT method initializes a NET_POWER_OFFLOAD_LIST structure.
tech.root: netvista
ms.assetid: 69577bdf-fff6-498f-ba80-fb1678e8145f
ms.author: windowsdriverdev
ms.date: 11/06/2019
ms.topic: function
f1_keywords:
 - "netpoweroffloadlist/NET_POWER_OFFLOAD_NS_PARAMETERS"
ms.keywords: NET_POWER_OFFLOAD_LIST_INIT
req.header: netpoweroffloadlist.h
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
- netpoweroffloadlist.h
api_name: 
- NET_POWER_OFFLOAD_LIST_INIT
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NET_POWER_OFFLOAD_LIST_INIT function


## -description

The **NET_POWER_OFFLOAD_LIST_INIT** method initializes a [**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md) structure.

## -parameters

### -param List

A handle to a driver-allocated [**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md) structure.

## -returns

This method does not return a value.

## -remarks

This method zeros out the memory for the **NET_POWER_OFFLOAD_LIST** structure, then fills in the **Size** member. After calling this method, call [**NetDeviceGetPowerOffloadList**](../netpoweroffloadlist/nf-netpoweroffloadlist-netdevicegetpoweroffloadlist.md) with the initialized structure to get the list of low power offloads to this net adapter.

The client driver must only call **NET_POWER_OFFLOAD_LIST_INIT** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

For a code sample of working with NETPOWEROFFLOAD objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md)

[**NetDeviceGetPowerOffloadList**](../netpoweroffloadlist/nf-netpoweroffloadlist-netdevicegetpoweroffloadlist.md)