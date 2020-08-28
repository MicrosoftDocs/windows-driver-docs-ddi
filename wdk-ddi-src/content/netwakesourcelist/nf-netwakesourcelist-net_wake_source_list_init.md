---
UID: NF:netwakesourcelist.NET_WAKE_SOURCE_LIST_INIT
title: NET_WAKE_SOURCE_LIST_INIT function (netwakesourcelist.h)
author: windows-driver-content
description: The NET_WAKE_SOURCE_LIST_INIT function initializes a NET_WAKE_SOURCE_LIST structure.
tech.root: netvista
ms.assetid: ec713591-4ac2-4f68-888d-e29c8784d8b6
ms.author: windowsdriverdev
ms.date: 10/08/2019
keywords: ["NET_WAKE_SOURCE_LIST_INIT function"]
f1_keywords:
 - "netwakesourcelist/NET_WAKE_SOURCE_LIST_INIT"
 - "NET_WAKE_SOURCE_LIST_INIT"
ms.keywords: NET_WAKE_SOURCE_LIST_INIT
req.header: netwakesourcelist.h
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
- netwakesourcelist.h
api_name: 
- NET_WAKE_SOURCE_LIST_INIT
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NET_WAKE_SOURCE_LIST_INIT function


## -description

The **NET_WAKE_SOURCE_LIST_INIT** function initializes a [**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md) structure.

## -parameters

### -param List

A pointer to a driver-allocated [**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md) structure.

## -returns

This function does not return a value.

## -remarks

This function zeroes out the memory for the **NET_WAKE_SOURCE_LIST** structure, then fills in the **Size** member. After calling this function, call [**NetDeviceGetWakeSourceList**](../netwakesourcelist/nf-netwakesourcelist-netdevicegetwakesourcelist.md) with the initialized structure to get the list of wake sources for this net adapter.

The client driver must only call **NET_WAKE_SOURCE_LIST_INIT** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

For a code sample of working with NETWAKESOURCE objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md)

[**NetDeviceGetWakeSourceList**](../netwakesourcelist/nf-netwakesourcelist-netdevicegetwakesourcelist.md)
