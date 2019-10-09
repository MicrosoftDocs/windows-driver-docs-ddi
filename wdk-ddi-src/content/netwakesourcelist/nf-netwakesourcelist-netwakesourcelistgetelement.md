---
UID: NF:netwakesourcelist.NetWakeSourceListGetElement
title: NetWakeSourceListGetElement function (netwakesourcelist.h)
author: windows-driver-content
description: TBD
tech.root:
ms.assetid: 6505fee3-68c7-4b65-a725-1d9072eeaa98
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
f1_keywords:
 - "netwakesourcelist/NetWakeSourceListGetElement"
ms.keywords: NetWakeSourceListGetElement
req.header: netwakesourcelist.h
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
- NetWakeSourceListGetElement
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetWakeSourceListGetElement function


## -description

The **NetWakeSourceListGetElement** method gets a NETWAKESOURCE object from a list of wake sources for a net adapter.

## -parameters

### -param List

A handle to a driver-allocated and initialized [**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md) structure.

### -param Index

The zero-based index in the list for the target NETWAKESOURCE object. This method must be less than the value returned by [**NetWakeSourceListGetCount**](../netwakesourcelist/nf-netwakesourcelist-netwakesourcelistgetcount.md).

## -returns

Returns the NETWAKESOURCE object at the specified index in the list.

## -remarks

Call [**NetWakeSourceListGetCount**](../netwakesourcelist/nf-netwakesourcelist-netwakesourcelistgetcount.md) to get the number of wake sources before calling this method.

The client driver must only call **NetWakeSourceListGetElement** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

For a code sample of working with NETWAKESOURCE objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md)

[**NetWakeSourceListGetCount**](../netwakesourcelist/nf-netwakesourcelist-netwakesourcelistgetcount.md)