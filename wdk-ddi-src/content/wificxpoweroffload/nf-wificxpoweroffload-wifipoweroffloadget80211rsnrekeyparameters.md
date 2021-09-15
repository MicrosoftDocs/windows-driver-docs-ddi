---
UID: NF:wificxpoweroffload.WifiPowerOffloadGet80211RSNRekeyParameters
tech.root: netvista
title: WifiPowerOffloadGet80211RSNRekeyParameters
ms.date: 09/15/2021
targetos: Windows
description: The WifiPowerOffloadGet80211RSNRekeyParameters function gets parameters for an 802.11 RSN rekey low power protocol offload to a WiFiCx net adapter.
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
 - WifiPowerOffloadGet80211RSNRekeyParameters
f1_keywords:
 - WifiPowerOffloadGet80211RSNRekeyParameters
 - wificxpoweroffload/WifiPowerOffloadGet80211RSNRekeyParameters
dev_langs:
 - c++
---

## -description

The **WifiPowerOffloadGet80211RSNRekeyParameters** function gets parameters for an 802.11 RSN rekey low power protocol offload to a WiFiCx net adapter.

## -parameters

### -param WifiPowerOffload

The WIFIPOWEROFFLOAD object that represents this protocol offload.

### -param Parameters

A pointer to a driver-allocated and initialized [**WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS**](ns-wificxpoweroffload-wifi_power_offload_80211rsnrekey_parameters.md) structure that receives the ARP parameter information.

## -remarks

Call [**WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS_INIT**](nf-wificxpoweroffload-wifi_power_offload_80211rsnrekey_parameters_init.md) to initialize the [**WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS**](ns-wificxpoweroffload-wifi_power_offload_80211rsnrekey_parameters.md) structure before calling this function.

The client driver must only call **WifiPowerOffloadGet80211RSNRekeyParameters** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS**](ns-wificxpoweroffload-wifi_power_offload_80211rsnrekey_parameters.md)

[**WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS_INIT**](nf-wificxpoweroffload-wifi_power_offload_80211rsnrekey_parameters_init.md)
