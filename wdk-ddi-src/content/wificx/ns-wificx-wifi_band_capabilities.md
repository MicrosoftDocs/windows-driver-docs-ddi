---
UID: NS:wificx._WIFI_BAND_CAPABILITIES
tech.root: netvista
title: WIFI_BAND_CAPABILITIES (wificx.h)
ms.date: 08/27/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_BAND_CAPABILITIES structure describes the band capabilities for a WiFiCx device.
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
req.typenames: WIFI_BAND_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_BAND_CAPABILITIES
 - WIFI_BAND_CAPABILITIES
f1_keywords:
 - _WIFI_BAND_CAPABILITIES
 - wificx/_WIFI_BAND_CAPABILITIES
 - WIFI_BAND_CAPABILITIES
 - wificx/WIFI_BAND_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **WIFI_BAND_CAPABILITIES** structure describes the band capabilities for a WiFiCx device.

## -struct-fields

### -field Size

The sum (in bytes) of the sizes of all contained elements.

### -field NumBands

The number of bands supported. 

### -field BandInfoList

A pointer to a list of [**WIFI_BAND_INFO**](ns-wificx-wifi_band_info.md) structures.

## -remarks

Client drivers pass **WIFI_BAND_CAPABILITIES** as a parameter to [**WifiDeviceSetBandCapabilities**](nf-wificx-wifidevicesetbandcapabilities.md) to report band capabilities to WiFiCx.


## -see-also

[**WIFI_BAND_INFO**](ns-wificx-wifi_band_info.md)

[**WifiDeviceSetBandCapabilities**](nf-wificx-wifidevicesetbandcapabilities.md)