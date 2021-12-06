---
UID: NF:wificx.WifiAdapterPowerOffloadSetRsnRekeyCapabilities
tech.root: netvista
title: WifiAdapterPowerOffloadSetRsnRekeyCapabilities
ms.date: 09/14/2021
targetos: Windows
description: The WifiAdapterPowerOffloadSetRsnRekeyCapabilities function sets a WiFiCx net adapter's RSN rekey power offload capabilities.
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
 - WifiAdapterPowerOffloadSetRsnRekeyCapabilities
f1_keywords:
 - WifiAdapterPowerOffloadSetRsnRekeyCapabilities
 - wificx/WifiAdapterPowerOffloadSetRsnRekeyCapabilities
dev_langs:
 - c++
---

## -description

The **WifiAdapterPowerOffloadSetRsnRekeyCapabilities** function sets a WiFiCx net adapter's RSN rekey power offload capabilities.

## -parameters

### -param Adapter

[_In_] A handle to a NetAdapterCx NETADAPTER object obtained in a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Capabilities

[_In_] A pointer to a driver-allocated and initialized [**WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES**](ns-wificx-wifi_adapter_power_offload_rsn_rekey_capabilities.md) structure.

## -remarks

The client driver typically calls this function from within [*EVT_DEVICE_PREPARE_HARDWARE*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md).

## -see-also

[**WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES**](ns-wificx-wifi_adapter_power_offload_rsn_rekey_capabilities.md)