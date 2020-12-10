---
UID: NF:netpoweroffloadlist.NetPowerOffloadListGetCount
title: NetPowerOffloadListGetCount function (netpoweroffloadlist.h)
description: The NetPowerOffloadListGetCount function gets the number of low power protocol offloads to a net adapter.
tech.root: netvista
ms.date: 10/03/2019
keywords: ["NetPowerOffloadListGetCount function"]
ms.keywords: NetPowerOffloadListGetCount
req.header: netpoweroffloadlist.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
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
 - NetPowerOffloadListGetCount
 - netpoweroffloadlist/NetPowerOffloadListGetCount
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetPowerOffloadListGetCount
product:
 - Windows
---

# NetPowerOffloadListGetCount function


## -description

The **NetPowerOffloadListGetCount** function gets the number of low power protocol offloads to a net adapter.

## -parameters

### -param List

A pointer to a driver-allocated and initialized [**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md) structure.

## -returns

Returns the number of low power offloads to this net adapter.

## -remarks

Call [**NET_POWER_OFFLOAD_LIST_INIT**](../netpoweroffloadlist/nf-netpoweroffloadlist-net_power_offload_list_init.md) to initialize the [**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md) structure, then call [**NetDeviceGetPowerOffloadList**](../netpoweroffloadlist/nf-netpoweroffloadlist-netdevicegetpoweroffloadlist.md) to retrieve the low power protocol offload list. After getting the list, call this function to determine how many low power protocol offloads there are to this net adapter.

The client driver must only call **NetPowerOffloadListGetCount** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

For a code sample of working with NETPOWEROFFLOAD objects, see [Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_LIST_INIT**](../netpoweroffloadlist/nf-netpoweroffloadlist-net_power_offload_list_init.md)

[**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md)

[**NetDeviceGetPowerOffloadList**](../netpoweroffloadlist/nf-netpoweroffloadlist-netdevicegetpoweroffloadlist.md)
