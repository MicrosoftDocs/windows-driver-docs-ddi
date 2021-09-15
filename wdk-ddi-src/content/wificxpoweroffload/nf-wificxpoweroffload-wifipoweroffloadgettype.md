---
UID: NF:wificxpoweroffload.WifiPowerOffloadGetType
tech.root: netvista
title: WifiPowerOffloadGetType (wificxpoweroffload.h)
ms.date: 09/10/2021
targetos: Windows
description: The WifiPowerOffloadGetType function gets the power offload type for a low power protocol offload to a WiFiCx net adapter.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificxpoweroffload.h
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
 - wificxpoweroffload.h
api_name:
 - WifiPowerOffloadGetType
f1_keywords:
 - WifiPowerOffloadGetType
 - wificxpoweroffload/WifiPowerOffloadGetType
dev_langs:
 - c++
---

## -description

The **WifiPowerOffloadGetType** function gets the Wi-Fi power offload type for a low power protocol offload to a WiFiCx net adapter.

## -parameters

### -param WifiPowerOffload

[_In_] A WIFIPOWEROFFLOAD object that represents this low power protocol offload.

## -returns

Returns a [**WIFI_POWER_OFFLOAD_TYPE**](ne-wificxpoweroffload-wifi_power_offload_type.md) value that specifies the offload type.

## -remarks

The client driver must only call **WifiPowerOffloadGetType** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**WIFI_POWER_OFFLOAD_TYPE**](ne-wificxpoweroffload-wifi_power_offload_type.md)