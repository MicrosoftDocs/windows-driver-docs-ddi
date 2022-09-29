---
UID: NF:wificx.WifiAdapterSetWakeCapabilities
tech.root: netvista
title: WifiAdapterSetWakeCapabilities
ms.date: 09/14/2021
targetos: Windows
description: The WifiAdapterSetWakeCapabilities method sets the wake capabilities for a WiFiCx device.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
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
 - wificx.h
api_name:
 - WifiAdapterSetWakeCapabilities
f1_keywords:
 - WifiAdapterSetWakeCapabilities
 - wificx/WifiAdapterSetWakeCapabilities
dev_langs:
 - c++
---

## -description

The **WifiAdapterSetWakeCapabilities** method sets the wake capabilities for a WiFiCx device.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Capabilities

[_In_] A pointer to a driver-allocated and initialized [**WIFI_ADAPTER_WAKE_CAPABILITIES**](ns-wificx-wifi_adapter_wake_capabilities.md) structure.

## -remarks

The client driver typically calls this function from within [*EVT_DEVICE_PREPARE_HARDWARE*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md).

## -see-also

[**WIFI_ADAPTER_WAKE_CAPABILITIES**](ns-wificx-wifi_adapter_wake_capabilities.md) 
