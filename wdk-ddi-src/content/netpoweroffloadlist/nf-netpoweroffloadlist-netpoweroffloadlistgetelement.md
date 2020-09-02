---
UID: NF:netpoweroffloadlist.NetPowerOffloadListGetElement
title: NetPowerOffloadListGetElement function (netpoweroffloadlist.h)
author: windows-driver-content
description: The NetPowerOffloadListGetElement function gets a low power protocol offload from a list of offloads to a net adapter.
tech.root: netvista
ms.assetid: a93ff9b6-6415-4d3f-8443-9a2479d88453
ms.author: windowsdriverdev
ms.date: 10/03/2019
keywords: ["NetPowerOffloadListGetElement function"]
ms.keywords: NetPowerOffloadListGetElement
req.header: netpoweroffloadlist.h
req.include-header: 
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
 - NetPowerOffloadListGetElement
 - netpoweroffloadlist/NetPowerOffloadListGetElement
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetPowerOffloadListGetElement
product:
 - Windows
---

# NetPowerOffloadListGetElement function


## -description

The **NetPowerOffloadListGetElement** function gets a low power protocol offload from a list of offloads to a net adapter.

## -parameters

### -param List

A pointer to a driver-allocated and initialized [**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md) structure.

### -param Index

The zero-based index in the list for the target NETPOWEROFFLOAD object. This function must be less than the value returned by [**NetPowerOffloadListGetCount**](../netpoweroffloadlist/nf-netpoweroffloadlist-netpoweroffloadlistgetcount.md).

## -returns

Returns the NETPOWEROFFLOAD object, which represents the low power protocol offload, at the specified index in the list.

## -remarks

Call [**NetPowerOffloadListGetCount**](../netpoweroffloadlist/nf-netpoweroffloadlist-netpoweroffloadlistgetcount.md) to get the number of low power protocol offloads before calling this function.

The client driver must only call **NetPowerOffloadListGetElement** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

For a code sample of working with NETPOWEROFFLOAD objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md)

[**NetPowerOffloadListGetCount**](../netpoweroffloadlist/nf-netpoweroffloadlist-netpoweroffloadlistgetcount.md)

