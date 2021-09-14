---
UID: NF:wificxpoweroffloadlist.WifiPowerOffloadListGetCount
tech.root: netvista
title: WifiPowerOffloadListGetCount (wificxpoweroffloadlist.h)
ms.date: 09/14/2021
targetos: Windows
description: The WifiPowerOffloadListGetCount function gets the number of low power protocol offloads to a Wi-Fi adapter.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificxpoweroffloadlist.h
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
 - LibDef
api_location:
 - wificxpoweroffloadlist.h
api_name:
 - WifiPowerOffloadListGetCount
f1_keywords:
 - WifiPowerOffloadListGetCount
 - wificxpoweroffloadlist/WifiPowerOffloadListGetCount
dev_langs:
 - c++
---

## -description

The **WifiPowerOffloadListGetCount** function gets the number of low power protocol offloads to a Wi-Fi adapter.

## -parameters

### -param List

[_In_] A pointer to a driver-allocated and initialized [**WIFI_POWER_OFFLOAD_LIST**](../wificxpoweroffloadlist/ns-wificxpoweroffloadlist-wifi_power_offload_list.md) structure.

## -returns

Returns the number of low power offloads to this Wi-Fi adapter.

## -remarks

Call [**WIFI_POWER_OFFLOAD_LIST_INIT**](nf-wificxpoweroffloadlist-wifi_power_offload_list_init.md) to initialize the [**WIFI_POWER_OFFLOAD_LIST**](../wificxpoweroffloadlist/ns-wificxpoweroffloadlist-wifi_power_offload_list.md) structure, then call [**WifiDeviceGetPowerOffloadList**](nf-wificxpoweroffloadlist-wifidevicegetpoweroffloadlist.md) to retrieve the low power protocol offload list. After getting the list, call this function to determine how many low power protocol offloads there are to this Wi-Fi adapter.

The client driver must only call **WifiPowerOffloadListGetCount** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**WIFI_POWER_OFFLOAD_LIST**](../wificxpoweroffloadlist/ns-wificxpoweroffloadlist-wifi_power_offload_list.md)

[**WIFI_POWER_OFFLOAD_LIST_INIT**](nf-wificxpoweroffloadlist-wifi_power_offload_list_init.md)

[**WifiDeviceGetPowerOffloadList**](nf-wificxpoweroffloadlist-wifidevicegetpoweroffloadlist.md)