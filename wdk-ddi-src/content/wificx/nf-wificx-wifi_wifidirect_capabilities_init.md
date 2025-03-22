---
UID: NF:wificx.WIFI_WIFIDIRECT_CAPABILITIES_INIT
tech.root: netvista
title: WIFI_WIFIDIRECT_CAPABILITIES_INIT
ms.date: 03/06/2024
targetos: Windows
description: The WIFI_WIFIDIRECT_CAPABILITIES_INIT function initializes a WIFI_WIFIDIRECT_CAPABILITIES structure.
prerelease: 
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
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
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
 - WIFI_WIFIDIRECT_CAPABILITIES_INIT
f1_keywords:
 - WIFI_WIFIDIRECT_CAPABILITIES_INIT
 - wificx/WIFI_WIFIDIRECT_CAPABILITIES_INIT
dev_langs:
 - c++
helpviewer_keywords:
 - WIFI_WIFIDIRECT_CAPABILITIES_INIT
---

# WIFI_WIFIDIRECT_CAPABILITIES_INIT function (wificx.h)

## -description

The **WIFI_WIFIDIRECT_CAPABILITIES_INIT** function initializes a [**WIFI_WIFIDIRECT_CAPABILITIES**](ns-wificx-wifi_wifidirect_capabilities.md) structure.

## -parameters

### -param Capabilities

[_Out_] A pointer to a client driver-allocated **WIFI_WIFIDIRECT_CAPABILITIES** structure.

## -remarks

This function zeroes out the memory of the **WIFI_WIFIDIRECT_CAPABILITIES** structure, then fills in the **Size** member. Client drivers must then call [**WifiDeviceSetWifiDirectCapabilities**](nf-wificx-wifidevicesetwifidirectcapabilities.md) to report WiFi Direct capabilities to WiFiCx.

## -see-also

[**WIFI_WIFIDIRECT_CAPABILITIES**](ns-wificx-wifi_wifidirect_capabilities.md)

[**WifiDeviceSetWifiDirectCapabilities**](nf-wificx-wifidevicesetwifidirectcapabilities.md)

