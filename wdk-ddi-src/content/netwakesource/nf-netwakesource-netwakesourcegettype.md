---
UID: NF:netwakesource.NetWakeSourceGetType
title: NetWakeSourceGetType function (netwakesource.h)
description: The NetWakeSourceGetType function gets the type for wake-on-LAN (WoL) source.
tech.root: netvista
ms.assetid: 05e0ca0e-5cf2-43b6-b5e1-325a11fde2da
ms.date: 10/10/2019
keywords: ["NetWakeSourceGetType function"]
ms.keywords: NetWakeSourceGetType
req.header: netwakesource.h
req.include-header: netadaptercx.h 
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NetWakeSourceGetType
 - netwakesource/NetWakeSourceGetType
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetWakeSourceGetType
product:
 - Windows
---

# NetWakeSourceGetType function


## -description

The **NetWakeSourceGetType** function gets the type for wake-on-LAN (WoL) source.

## -parameters

### -param WakeSource

The NETWAKESOURCE object that represents this wake source.

## -returns

Returns a [**NET_WAKE_SOURCE_TYPE**](../netwakesource/ne-netwakesource-_net_wake_source_type.md) value that specifies the wake source type.

## -remarks

The client driver must only call **NetWakeSourceGetType** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_TYPE**](../netwakesource/ne-netwakesource-_net_wake_source_type.md)

[**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md)

