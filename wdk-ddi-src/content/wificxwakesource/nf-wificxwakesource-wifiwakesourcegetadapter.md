---
UID: NF:wificxwakesource.WifiWakeSourceGetAdapter
tech.root: netvista
title: WifiWakeSourceGetAdapter (wificxwakesource.h)
ms.date: 09/14/2021
targetos: Windows
description: The WifiWakeSourceGetAdapter function gets the WiFiCx net adapter for a wake-up source.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificxwakesource.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificxwakesource.h
api_name:
 - WifiWakeSourceGetAdapter
f1_keywords:
 - WifiWakeSourceGetAdapter
 - wificxwakesource/WifiWakeSourceGetAdapter
dev_langs:
 - c++
---

## -description

The **WifiWakeSourceGetAdapter** function gets the WiFiCx net adapter for a wake-up source.

## -parameters

### -param WakeSource

[_In_] The WIFIWAKESOURCE object that represents the source of the wake-up event.

## -returns

Returns the NETADAPTER object that represents the Wi-Fi adapter for this wake source.

## -remarks

The client driver must only call **WifiWakeSourceGetAdapter** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

