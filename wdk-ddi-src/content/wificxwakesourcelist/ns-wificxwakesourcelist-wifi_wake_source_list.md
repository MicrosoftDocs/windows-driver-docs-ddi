---
UID: NS:wificxwakesourcelist._WIFI_WAKE_SOURCE_LIST
tech.root: netvista
title: WIFI_WAKE_SOURCE_LIST (wificxwakesourcelist.h)
ms.date: 09/14/2021
targetos: Windows
description: The WIFI_WAKE_SOURCE_LIST structure represents a list of wake sources for a WiFiCx net adapter.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificxwakesourcelist.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_WAKE_SOURCE_LIST
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificxwakesourcelist.h
api_name:
 - _WIFI_WAKE_SOURCE_LIST
 - WIFI_WAKE_SOURCE_LIST
f1_keywords:
 - _WIFI_WAKE_SOURCE_LIST
 - wificxwakesourcelist/_WIFI_WAKE_SOURCE_LIST
 - WIFI_WAKE_SOURCE_LIST
 - wificxwakesourcelist/WIFI_WAKE_SOURCE_LIST
dev_langs:
 - c++
---

## -description

The **WIFI_WAKE_SOURCE_LIST** structure represents a list of wake sources for a WiFiCx net adapter.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field Reserved

Reserved. Client drivers must not read or write to this value directly.

## -remarks

Call [**WIFI_WAKE_SOURCE_LIST_INIT**](nf-wificxwakesourcelist-wifi_wake_source_list_init.md) to initialize this structure, then call [**WifiDeviceGetWakeSourceList**](nf-wificxwakesourcelist-wifidevicegetwakesourcelist.md) to get the list of wake sources from this net adapter. After you obtain the list, call [**WifiWakeSourceListGetCount**](nf-wificxwakesourcelist-wifiwakesourcelistgetcount.md) with this structure to get the number of WIFIWAKESOURCE objects that represents the wake sources, then loop over the objects and call [**WifiWakeSourceListGetElement**](nf-wificxwakesourcelist-wifiwakesourcelistgetelement.md) to retrieve each one. Once you have obtained a WIFIWAKESOURCE object, call [**WifiWakeSourceGetType**](../wificxwakesource/nf-wificxwakesource-wifiwakesourcegettype.md) to get the type of that wake source so you can call the appropriate function to get the wake source's parameters.

The client driver must only call wake source-related functions during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**WIFI_WAKE_SOURCE_LIST_INIT**](nf-wificxwakesourcelist-wifi_wake_source_list_init.md)

[**WifiDeviceGetWakeSourceList**](nf-wificxwakesourcelist-wifidevicegetwakesourcelist.md)

[**WifiWakeSourceListGetCount**](nf-wificxwakesourcelist-wifiwakesourcelistgetcount.md)

[**WifiWakeSourceListGetElement**](nf-wificxwakesourcelist-wifiwakesourcelistgetelement.md)

[**WifiWakeSourceGetType**](../wificxwakesource/nf-wificxwakesource-wifiwakesourcegettype.md)