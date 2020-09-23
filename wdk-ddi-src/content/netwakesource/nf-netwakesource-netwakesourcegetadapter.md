---
UID: NF:netwakesource.NetWakeSourceGetAdapter
title: NetWakeSourceGetAdapter function (netwakesource.h)
description: The NetWakeSourceGetAdapter function gets the net adapter for a wake-on-LAN (WoL) source.
tech.root: netvista
ms.assetid: 75706f44-2e82-420d-a435-73ee32e5090a
ms.author: windowsdriverdev
ms.date: 10/07/2019
keywords: ["NetWakeSourceGetAdapter function"]
ms.keywords: NetWakeSourceGetAdapter
req.header: netwakesource.h
req.include-header: netadaptercx.h 
req.target-type: 
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
 - NetWakeSourceGetAdapter
 - netwakesource/NetWakeSourceGetAdapter
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetWakeSourceGetAdapter
product:
 - Windows
---

# NetWakeSourceGetAdapter function


## -description

The **NetWakeSourceGetAdapter** function gets the net adapter for a wake-on-LAN (WoL) source.

## -parameters

### -param WakeSource

The NETWAKESOURCE object that represents the source of the wake-up event.

## -returns

Returns the NETADAPTER object that represents the net adapter for this wake source.

## -remarks

Client drivers that have one network adapter per device do not need to call this optional function. Call **NetWakeSourceGetAdapter** if your device has more than one net adapter object per device, such as in a [MBBCx client driver](https://docs.microsoft.com/windows-hardware/drivers/netcx/mobile-broadband-mbb-wdf-class-extension-mbbcx).

The client driver must only call **NetWakeSourceGetAdapter** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NetWakeSourceListGetElement**]

