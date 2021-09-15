---
UID: NF:wificxpoweroffloadlist.WifiDeviceGetPowerOffloadList
tech.root: netvista
title: WifiDeviceGetPowerOffloadList (wificxpoweroffloadlist.h)
ms.date: 09/10/2021
targetos: Windows
description: The WifiDeviceGetPowerOffloadList function gets the list of low power protocol offloads to a WiFiCx net adapter.
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
 - WifiDeviceGetPowerOffloadList
f1_keywords:
 - WifiDeviceGetPowerOffloadList
 - wificxpoweroffloadlist/WifiDeviceGetPowerOffloadList
dev_langs:
 - c++
---

## -description

The **WifiDeviceGetPowerOffloadList** function gets the list of low power protocol offloads to a WiFiCx net adapter.


## -parameters

### -param Device

[_In_] The WDFDEVICE object associated with the WiFiCx net adapter.

### -param List

[_Inout_] A pointer to a driver-allocated and initialized [**WIFI_POWER_OFFLOAD_LIST**](ns-wificxpoweroffloadlist-wifi_power_offload_list.md) structure.

## -remarks

Call [**WIFI_POWER_OFFLOAD_LIST_INIT**](nf-wificxpoweroffloadlist-wifi_power_offload_list_init.md) to initialize the [**WIFI_POWER_OFFLOAD_LIST**](ns-wificxpoweroffloadlist-wifi_power_offload_list.md) structure, then call this function to retrieve the low power protocol offload list.

The client driver must only call **WifiDeviceGetPowerOffloadList** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**WIFI_POWER_OFFLOAD_LIST**](ns-wificxpoweroffloadlist-wifi_power_offload_list.md)

[**WIFI_POWER_OFFLOAD_LIST_INIT**](nf-wificxpoweroffloadlist-wifi_power_offload_list_init.md)