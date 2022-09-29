---
UID: NF:wificxwakesourcelist.WifiWakeSourceListGetCount
tech.root: netvista
title: WifiWakeSourceListGetCount (wificxwakesourcelist.h)
ms.date: 09/14/2021
targetos: Windows
description: The WifiWakeSourceListGetCount function gets the number of wake sources for a WiFiCx net adapter.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificxwakesourcelist.h
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
 - wificxwakesourcelist.h
api_name:
 - WifiWakeSourceListGetCount
f1_keywords:
 - WifiWakeSourceListGetCount
 - wificxwakesourcelist/WifiWakeSourceListGetCount
dev_langs:
 - c++
---

## -description

The **WifiWakeSourceListGetCount** function gets the number of wake sources for a WiFiCx net adapter.

## -parameters

### -param List

[_In_] A pointer to a driver-allocated and initialized [**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md) structure.

## -returns

Returns the number of wake sources for this net adapter.

## -remarks

Call [**WIFI_WAKE_SOURCE_LIST_INIT**](nf-wificxwakesourcelist-wifi_wake_source_list_init.md) to initialize the [**WIFI_WAKE_SOURCE_LIST**](ns-wificxwakesourcelist-wifi_wake_source_list.md) structure, then call [**WifiDeviceGetWakeSourceList**](nf-wificxwakesourcelist-wifidevicegetwakesourcelist.md) to retrieve the wake source list. After getting the list, call this function to determine how many wake sources there are for this net adapter.

The client driver must only call **WifiWakeSourceListGetCount** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**NET_WAKE_SOURCE_LIST**](../netwakesourcelist/ns-netwakesourcelist-_net_wake_source_list.md)