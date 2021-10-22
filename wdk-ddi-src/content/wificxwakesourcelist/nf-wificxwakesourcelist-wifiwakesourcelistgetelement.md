---
UID: NF:wificxwakesourcelist.WifiWakeSourceListGetElement
tech.root: netvista
title: WifiWakeSourceListGetElement (wificxwakesourcelist.h)
ms.date: 09/14/2021
targetos: Windows
description: The WifiWakeSourceListGetElement function gets a wake source from the list of wake sources for a WiFiCx net adapter.
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
 - WifiWakeSourceListGetElement
f1_keywords:
 - WifiWakeSourceListGetElement
 - wificxwakesourcelist/WifiWakeSourceListGetElement
dev_langs:
 - c++
---

## -description

The **WifiWakeSourceListGetElement** function gets a wake source from the list of wake sources for a WiFiCx net adapter.

## -parameters

### -param List

[_In_] A handle to a driver-allocated and initialized [**WIFI_WAKE_SOURCE_LIST**](ns-wificxwakesourcelist-wifi_wake_source_list.md) structure.

### -param Index

[_In_] The zero-based index in the list for the target WIFIWAKESOURCE object. This function must be less than the value returned by [**WifiWakeSourceListGetCount**](nf-wificxwakesourcelist-wifiwakesourcelistgetcount.md).

## -returns

Returns the WIFIWAKESOURCE object, which represents the wake source, at the specified index in the list.

## -remarks

Call [**WifiWakeSourceListGetCount**](nf-wificxwakesourcelist-wifiwakesourcelistgetcount.md) to get the number of wake sources before calling this function.

The client driver must only call **WifiWakeSourceListGetElement** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.


## -see-also

[**WIFI_WAKE_SOURCE_LIST**](ns-wificxwakesourcelist-wifi_wake_source_list.md)

[**WifiWakeSourceListGetCount**](nf-wificxwakesourcelist-wifiwakesourcelistgetcount.md)