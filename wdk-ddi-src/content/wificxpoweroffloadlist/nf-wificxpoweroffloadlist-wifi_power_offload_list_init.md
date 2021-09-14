---
UID: NF:wificxpoweroffloadlist.WIFI_POWER_OFFLOAD_LIST_INIT
tech.root: netvista
title: WIFI_POWER_OFFLOAD_LIST_INIT (wificxpoweroffloadlist.h)
ms.date: 09/10/2021
targetos: Windows
description: The WIFI_POWER_OFFLOAD_LIST_INIT function initializes a WIFI_POWER_OFFLOAD_LIST structure. 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificxpoweroffloadlist.h
req.idl: 
req.include-header: 
req.irql: 
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
 - WIFI_POWER_OFFLOAD_LIST_INIT
f1_keywords:
 - WIFI_POWER_OFFLOAD_LIST_INIT
 - wificxpoweroffloadlist/WIFI_POWER_OFFLOAD_LIST_INIT
dev_langs:
 - c++
---

## -description

The **WIFI_POWER_OFFLOAD_LIST_INIT** function initializes a [**WIFI_POWER_OFFLOAD_LIST**](ns-wificxpoweroffloadlist-wifi_power_offload_list.md) structure. 

## -parameters

### -param List

[_Out_] A pointer to a driver-allocated [**WIFI_POWER_OFFLOAD_LIST**](ns-wificxpoweroffloadlist-wifi_power_offload_list.md).

## -remarks

This function zeroes out the memory of the [**WIFI_POWER_OFFLOAD_LIST**](ns-wificxpoweroffloadlist-wifi_power_offload_list.md) structure, then fills in the **Size** member. Client drivers must then call [**WifiDeviceGetPowerOffloadList**](nf-wificxpoweroffloadlist-wifidevicegetpoweroffloadlist.md) with the initialized structure to get the list of low power offloads to this Wi-Fi adapter.

The client driver must only call **WIFI_POWER_OFFLOAD_LIST_INIT** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**WIFI_POWER_OFFLOAD_LIST**](ns-wificxpoweroffloadlist-wifi_power_offload_list.md)

[**WifiDeviceGetPowerOffloadList**](nf-wificxpoweroffloadlist-wifidevicegetpoweroffloadlist.md)
