---
UID: NS:wificxpoweroffloadlist._WIFI_POWER_OFFLOAD_LIST
tech.root: netvista
title: WIFI_POWER_OFFLOAD_LIST (wificxpoweroffloadlist.h)
ms.date: 09/10/2021
targetos: Windows
description: The WIFI_POWER_OFFLOAD_LIST structure represents a list of low power protocol offloads to a Wi-Fi adapter.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificxpoweroffloadlist.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_POWER_OFFLOAD_LIST
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificxpoweroffloadlist.h
api_name:
 - _WIFI_POWER_OFFLOAD_LIST
 - WIFI_POWER_OFFLOAD_LIST
f1_keywords:
 - _WIFI_POWER_OFFLOAD_LIST
 - wificxpoweroffloadlist/_WIFI_POWER_OFFLOAD_LIST
 - WIFI_POWER_OFFLOAD_LIST
 - wificxpoweroffloadlist/WIFI_POWER_OFFLOAD_LIST
dev_langs:
 - c++
---

## -description

The **WIFI_POWER_OFFLOAD_LIST** structure represents a list of low power protocol offloads to a Wi-Fi adapter.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field Reserved

Reserved. Client drivers must not read or write to this value directly.

## -remarks

Call [**WIFI_POWER_OFFLOAD_LIST_INIT**](nf-wificxpoweroffloadlist-wifi_power_offload_list_init.md) to initialize this structure, then call [**WifiDeviceGetPowerOffloadList**](nf-wificxpoweroffloadlist-wifidevicegetpoweroffloadlist.md) to get the list of low power offloads to this Wi-Fi adapter. After you obtain the list, call [**WifiPowerOffloadListGetCount**](nf-wificxpoweroffloadlist-wifipoweroffloadlistgetcount.md) with this structure to get the number of WIFIPOWEROFFLOAD objects that represents the offloads, then loop over the objects and call [**WifiPowerOffloadListGetElement**](nf-wificxpoweroffloadlist-wifipoweroffloadlistgetelement.md) to retrieve each one. Once you have obtained a WIFIPOWEROFFLOAD object, call [**WifiPowerOffloadGetType**](../wificxpoweroffload.nf-wificxpoweroffload-wifipoweroffloadgettype.md) to get the type of that offload so you can call the appropriate function to get the offload's parameters.

The client driver must only call power offload-related functions during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**WIFI_POWER_OFFLOAD_LIST_INIT**](nf-wificxpoweroffloadlist-wifi_power_offload_list_init.md)

[**WifiDeviceGetPowerOffloadList**](nf-wificxpoweroffloadlist-wifidevicegetpoweroffloadlist.md) 

[**WifiPowerOffloadListGetCount**](nf-wificxpoweroffloadlist-wifipoweroffloadlistgetcount.md)

[**WifiPowerOffloadListGetElement**](nf-wificxpoweroffloadlist-wifipoweroffloadlistgetelement.md)

[**WifiPowerOffloadGetType**](../wificxpoweroffload.nf-wificxpoweroffload-wifipoweroffloadgettype.md)