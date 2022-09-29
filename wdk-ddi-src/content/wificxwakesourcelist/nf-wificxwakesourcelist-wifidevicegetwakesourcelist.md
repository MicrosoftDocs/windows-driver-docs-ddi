---
UID: NF:wificxwakesourcelist.WifiDeviceGetWakeSourceList
tech.root: netvista
title: WifiDeviceGetWakeSourceList (wificxwakesourcelist.h)
ms.date: 09/14/2021
targetos: Windows
description: The WifiDeviceGetWakeSourceList function gets the list of wake sources for a WiFiCx net adapter.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificxwakesourcelist.h
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
 - HeaderDef
api_location:
 - wificxwakesourcelist.h
api_name:
 - WifiDeviceGetWakeSourceList
f1_keywords:
 - WifiDeviceGetWakeSourceList
 - wificxwakesourcelist/WifiDeviceGetWakeSourceList
dev_langs:
 - c++
---

## -description

The **WifiDeviceGetWakeSourceList** function gets the list of wake sources for a WiFiCx net adapter.

## -parameters

### -param Device

The WDFDEVICE object that is associated with the net adapter (or multiple adapters if the client driver has more than one for this device).

### -param List

A pointer to a driver-allocated and initialized [**WIFI_WAKE_SOURCE_LIST**](ns-wificxwakesourcelist-wifi_wake_source_list.md) structure.

## -remarks

Call [**WIFI_WAKE_SOURCE_LIST_INIT**](nf-wificxwakesourcelist-wifi_wake_source_list_init.md) to initialize the [**WIFI_WAKE_SOURCE_LIST**](ns-wificxwakesourcelist-wifi_wake_source_list.md) structure, then call this function to retrieve the wake source list.

The client driver must only call **WifiDeviceGetWakeSourceList** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**WIFI_WAKE_SOURCE_LIST**](ns-wificxwakesourcelist-wifi_wake_source_list.md)

[**WIFI_WAKE_SOURCE_LIST_INIT**](nf-wificxwakesourcelist-wifi_wake_source_list_init.md)
