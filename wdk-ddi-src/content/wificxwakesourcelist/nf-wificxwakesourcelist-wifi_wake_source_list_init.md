---
UID: NF:wificxwakesourcelist.WIFI_WAKE_SOURCE_LIST_INIT
tech.root: netvista
title: WIFI_WAKE_SOURCE_LIST_INIT (wificxwakesourcelist.h)
ms.date: 09/14/2021
targetos: Windows
description: The WIFI_WAKE_SOURCE_LIST_INIT function initializes a WIFI_WAKE_SOURCE_LIST structure.
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
 - WIFI_WAKE_SOURCE_LIST_INIT
f1_keywords:
 - WIFI_WAKE_SOURCE_LIST_INIT
 - wificxwakesourcelist/WIFI_WAKE_SOURCE_LIST_INIT
dev_langs:
 - c++
---

## -description

The **WIFI_WAKE_SOURCE_LIST_INIT** function initializes a [**WIFI_WAKE_SOURCE_LIST**](ns-wificxwakesourcelist-wifi_wake_source_list.md) structure.

## -parameters

### -param List

[_Out_] A pointer to a driver-allocated [**WIFI_WAKE_SOURCE_LIST**](ns-wificxwakesourcelist-wifi_wake_source_list.md) structure.

## -remarks

This function zeroes out the memory for the **WIFI_WAKE_SOURCE_LIST** structure, then fills in the **Size** member. After calling this function, call [**WifiDeviceGetWakeSourceList**](nf-wificxwakesourcelist-wifidevicegetwakesourcelist.md) with the initialized structure to get the list of wake sources for this Wi-Fi adapter.

The client driver must only call **WIFI_WAKE_SOURCE_LIST_INIT** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**WIFI_WAKE_SOURCE_LIST**](ns-wificxwakesourcelist-wifi_wake_source_list.md)

[**WifiDeviceGetWakeSourceList**](nf-wificxwakesourcelist-wifidevicegetwakesourcelist.md)