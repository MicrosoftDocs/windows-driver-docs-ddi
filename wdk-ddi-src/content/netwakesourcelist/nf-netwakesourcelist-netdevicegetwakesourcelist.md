---
UID: NF:netwakesourcelist.NetDeviceGetWakeSourceList
title: NetDeviceGetWakeSourceList function (netwakesourcelist.h)
author: windows-driver-content
description: The NetDeviceGetWakeSourceList method gets the list of wake sources for a net adapter.
tech.root: netvista
ms.assetid: a70770b8-04a4-4012-9f1b-dcf62cdc5a8b
ms.author: windowsdriverdev
ms.date: 10/08/2019
keywords: ["NetDeviceGetWakeSourceList function"]
f1_keywords:
 - "netwakesourcelist/NetDeviceGetWakeSourceList"
 - "NetDeviceGetWakeSourceList"
ms.keywords: NetDeviceGetWakeSourceList
req.header: netwakesourcelist.h
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
- NetDeviceGetWakeSourceList
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetDeviceGetWakeSourceList function


## -description

The **NetDeviceGetWakeSourceList** method gets the list of wake sources for a net adapter.

## -parameters

### -param Device

The WDFDEVICE object that is associated with the net adapter (or multiple adapters if the client driver has more than one for this device).

### -param List

A pointer to a driver-allocated and initialized [**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md) structure.

## -returns

This method does not return a value.

## -remarks

Call [**NET_WAKE_SOURCE_LIST_INIT**](../netwakesourcelist/nf-netwakesourcelist-net_wake_source_list_init.md) to initialize the [**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md) structure, then call this method to retrieve the wake source list.

The client driver must only call **NetDeviceGetWakeSourceList** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

For a code sample of working with NETWAKESOURCE objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_LIST_INIT**](../netwakesourcelist/nf-netwakesourcelist-net_wake_source_list_init.md)

[**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md)
