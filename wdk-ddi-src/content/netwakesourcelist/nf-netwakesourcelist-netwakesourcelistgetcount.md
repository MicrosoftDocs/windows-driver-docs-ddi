---
UID: NF:netwakesourcelist.NetWakeSourceListGetCount
title: NetWakeSourceListGetCount function (netwakesourcelist.h)
author: windows-driver-content
description: The NetWakeSourceListGetCount method gets the number of wake sources for a net adapter.
tech.root: netvista
ms.assetid: 2380726e-eef7-43fb-aa6a-9109232eff1f
ms.author: windowsdriverdev
ms.date: 10/08/2019
keywords: ["NetWakeSourceListGetCount function"]
f1_keywords:
 - "netwakesourcelist/NetWakeSourceListGetCount"
ms.keywords: NetWakeSourceListGetCount
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
- NetWakeSourceListGetCount
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetWakeSourceListGetCount function


## -description

The **NetWakeSourceListGetCount** method gets the number of wake sources for a net adapter.

## -parameters

### -param List

A pointer to a driver-allocated and initialized [**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md) structure.

## -returns

Returns the number of wake sources for this net adapter.

## -remarks

Call [**NET_WAKE_SOURCE_LIST_INIT**](../netwakesourcelist/nf-netwakesourcelist-net_wake_source_list_init.md) to initialize the [**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md) structure, then call [**NetDeviceGetWakeSourceList**](../netwakesourcelist/nf-netwakesourcelist-netdevicegetwakesourcelist.md) to retrieve the wake source list. After getting the list, call this method to determine how many wake sources there are for this net adapter.

The client driver must only call **NetWakeSourceListGetCount** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

For a code sample of working with NETWAKESOURCE objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_LIST_INIT**](../netwakesourcelist/nf-netwakesourcelist-net_wake_source_list_init.md)

[**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md)

[**NetDeviceGetWakeSourceList**](../netwakesourcelist/nf-netwakesourcelist-netdevicegetwakesourcelist.md)
