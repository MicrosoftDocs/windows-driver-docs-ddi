---
UID: NS:wificx._WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES
tech.root: netvista
title: WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES
ms.date: 09/14/2021
targetos: Windows
description: The WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES structure describes a WiFiCx net adapter's RSN rekey power offload capabilities.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES
 - WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES
f1_keywords:
 - _WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES
 - wificx/_WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES
 - WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES
 - wificx/WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES** structure describes a WiFiCx net adapter's RSN rekey power offload capabilities.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field Enabled

Specifies if the adapter's RSN rekey power offload capabilities are enabled. 

## -remarks

Call [**WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES_INIT**](nf-wificx-wifi_adapter_power_offload_rsn_rekey_capabilities_init.md) to initialize this structure.

## -see-also

[**WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES_INIT**](nf-wificx-wifi_adapter_power_offload_rsn_rekey_capabilities_init.md)
