---
UID: NE:wwan._WWAN_SAR_WIFI_HARDWARE_INTEGRATION
title: _WWAN_SAR_WIFI_HARDWARE_INTEGRATION (wwan.h)
description: The WWAN_SAR_WIFI_HARDWARE_INTEGRATION enumeration specifies whether Wi-Fi and Cellular are integrated at the hardware level in a mobile broadband (MBB) modem.
tech.root: netvista
ms.assetid: 87721dbb-a9af-456f-b452-14cb0e11c0b9
ms.date: 08/20/2018
keywords: ["_WWAN_SAR_WIFI_HARDWARE_INTEGRATION enumeration"]
f1_keywords:
 - "wwan/_WWAN_SAR_WIFI_HARDWARE_INTEGRATION"
 - "_WWAN_SAR_WIFI_HARDWARE_INTEGRATION"
ms.keywords: _WWAN_SAR_WIFI_HARDWARE_INTEGRATION, WWAN_SAR_WIFI_HARDWARE_INTEGRATION, *PWWAN_SAR_WIFI_HARDWARE_INTEGRATION, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_SAR_WIFI_HARDWARE_INTEGRATION, *PWWAN_SAR_WIFI_HARDWARE_INTEGRATION
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_SAR_WIFI_HARDWARE_INTEGRATION
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_SAR_WIFI_HARDWARE_INTEGRATION enumeration

## -description

The **WWAN_SAR_WIFI_HARDWARE_INTEGRATION** enumeration specifies whether Wi-Fi and Cellular are integrated at the hardware level in a mobile broadband (MBB) modem.

## -enum-fields

### -field WwanSarWifiHardwareNotIntegrated 

Wi-Fi and Cellular modem SAR are integrated in the device.

### -field WwanSarWifiHardwareIntegrated 

Wi-Fi and Cellular modem SAR are not integrated in the device.

## -remarks

This enumeration is used in the [**WWAN_SAR_CONFIG_INFO**](ns-wwan-_wwan_sar_config_info.md) structure.

## -see-also

[MB SAR Platform Support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-sar-platform-support)

[OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config)

[**WWAN_SAR_CONFIG_INFO**](ns-wwan-_wwan_sar_config_info.md)
