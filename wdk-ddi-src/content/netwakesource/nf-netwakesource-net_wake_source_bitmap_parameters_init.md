---
UID: NF:netwakesource.NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT
title: NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT function (netwakesource.h)
author: windows-driver-content
description: The NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT method initializes a NET_WAKE_SOURCE_BITMAP_PARAMETERS structure.
tech.root: netvista
ms.assetid: 514ad478-31fd-455b-a793-cacec1c241cb
ms.author: windowsdriverdev
ms.date: 10/07/2019
ms.topic: function
f1_keywords:
 - "netwakesource/NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT"
ms.keywords: NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT
req.header: netwakesource.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: The next version of Windows 10
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
- netwakesource.h
api_name: 
- NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT function


## -description

The **NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT** method initializes a [**NET_WAKE_SOURCE_BITMAP_PARAMETERS**](../netwakesource/ns-netwakesource-_net_wake_source_bitmap_parameters.md) structure.

## -parameters

### -param Parameters

A pointer to a driver-allocated [**NET_WAKE_SOURCE_BITMAP_PARAMETERS**](../netwakesource/ns-netwakesource-_net_wake_source_bitmap_parameters.md) structure.

## -returns

This method does not return a value.

## -remarks

This method zeroes out the memory of the **NET_WAKE_SOURCE_BITMAP_PARAMETERS** structure, then fills in the **Size** member. Client drivers must then fill in the other members of the structure.

The client driver must only call **NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_BITMAP_PARAMETERS**](../netwakesource/ns-netwakesource-_net_wake_source_bitmap_parameters.md)