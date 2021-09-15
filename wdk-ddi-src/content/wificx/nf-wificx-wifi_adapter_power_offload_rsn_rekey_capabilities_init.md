---
UID: NF:wificx.WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES_INIT
tech.root: netvista
title: WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES_INIT (wificx.h)
ms.date: 09/14/2021
targetos: Windows
description: The WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES_INIT function initializes a WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES structure.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
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
 - wificx.h
api_name:
 - WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES_INIT
f1_keywords:
 - WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES_INIT
 - wificx/WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES_INIT
dev_langs:
 - c++
---

## -description

The **WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES_INIT** function initializes a [**WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES**](ns-wificx-wifi_adapter_power_offload_rsn_rekey_capabilities.md) structure.

## -parameters

### -param Capabilities

[_Out_] A pointer to a driver-allocated [**WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES**](ns-wificx-wifi_adapter_power_offload_rsn_rekey_capabilities.md) structure.

## -remarks

This function zeroes out the memory of the [**WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES**](ns-wificx-wifi_adapter_power_offload_rsn_rekey_capabilities.md) structure, fills in the **Size** member, and sets the **Enabled** member to **TRUE**.

Call [**WifiAdapterPowerOffloadSetRsnRekeyCapabilities**](nf-wificx-wifiadapterpoweroffloadsetrsnrekeycapabilities.md) to set the net adapter's RSN rekey power offload capabilities.

## -see-also

[**WIFI_ADAPTER_POWER_OFFLOAD_RSN_REKEY_CAPABILITIES**](ns-wificx-wifi_adapter_power_offload_rsn_rekey_capabilities.md)

[**WifiAdapterPowerOffloadSetRsnRekeyCapabilities**](nf-wificx-wifiadapterpoweroffloadsetrsnrekeycapabilities.md)