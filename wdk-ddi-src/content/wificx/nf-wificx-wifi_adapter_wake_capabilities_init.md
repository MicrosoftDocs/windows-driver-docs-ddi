---
UID: NF:wificx.WIFI_ADAPTER_WAKE_CAPABILITIES_INIT
tech.root: netvista
title: WIFI_ADAPTER_WAKE_CAPABILITIES_INIT (wificx.h)
ms.date: 09/14/2021
targetos: Windows
description: The WIFI_ADAPTER_WAKE_CAPABILITIES_INIT method initializes a WIFI_ADAPTER_WAKE_CAPABILITIES structure.
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
 - WIFI_ADAPTER_WAKE_CAPABILITIES_INIT
f1_keywords:
 - WIFI_ADAPTER_WAKE_CAPABILITIES_INIT
 - wificx/WIFI_ADAPTER_WAKE_CAPABILITIES_INIT
dev_langs:
 - c++
---

## -description

The **WIFI_ADAPTER_WAKE_CAPABILITIES_INIT** method initializes a [**WIFI_ADAPTER_WAKE_CAPABILITIES**](ns-wificx-wifi_adapter_wake_capabilities.md) structure.

## -parameters

### -param Capabilities

[_Out_] A pointer to a driver-allocated [**WIFI_ADAPTER_WAKE_CAPABILITIES**](ns-wificx-wifi_adapter_wake_capabilities.md) structure.

## -remarks

This methods zeroes out the memory of the  **WIFI_ADAPTER_WAKE_CAPABILITIES** structure, then fills in the **Size** member. After calling this method, set the remaining members of the  **WIFI_ADAPTER_WAKE_CAPABILITIES** structure according to your device's capabilities, then call [**WifiAdapterSetWakeCapabilities**](nf-wificx-wifiadaptersetwakecapabilities.md).

## -see-also

[**WIFI_ADAPTER_WAKE_CAPABILITIES**](ns-wificx-wifi_adapter_wake_capabilities.md)

[**WifiAdapterSetWakeCapabilities**](nf-wificx-wifiadaptersetwakecapabilities.md)