---
UID: NS:wificx._WIFI_PHY_CAPABILITIES
tech.root: netvista
title: WIFI_PHY_CAPABILITIES (wificx.h)
ms.date: 03/06/2024
targetos: Windows
description: The WIFI_PHY_CAPABILITIES structure describes the PHY capabilities for a WiFiCx device.
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
req.typenames: WIFI_PHY_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_PHY_CAPABILITIES
 - WIFI_PHY_CAPABILITIES
f1_keywords:
 - _WIFI_PHY_CAPABILITIES
 - wificx/_WIFI_PHY_CAPABILITIES
 - WIFI_PHY_CAPABILITIES
 - wificx/WIFI_PHY_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **WIFI_PHY_CAPABILITIES** structure describes the PHY capabilities for a WiFiCx device.

## -struct-fields

### -field Size

The sum (in bytes) of the sizes of all contained elements.

### -field NumPhyTypes

The number of PHY types supported. 

### -field PhyInfoList

A pointer to a list of [**WIFI_PHY_INFO**](ns-wificx-wifi_phy_info.md) structures.

## -remarks

Client drivers pass **WIFI_PHY_CAPABILITIES** as a parameter to [**WifiDeviceSetPhyCapabilities**](nf-wificx-wifidevicesetphycapabilities.md) to report PHY capabilities to WiFiCx.

Call [**WIFI_PHY_CAPABILITIES_INIT**](nf-wificx-wifi_phy_capabilities_init.md) to initialize this structure and fill in its **Size** field. Then call [**WifiDeviceSetPhyCapabilities**](nf-wificx-wifidevicesetphycapabilities.md) to report PHY capabilities to WiFiCx.

## -see-also

[**WIFI_PHY_CAPABILITIES_INIT**](nf-wificx-wifi_phy_capabilities_init.md)

[**WifiDeviceSetPhyCapabilities**](nf-wificx-wifidevicesetphycapabilities.md)

[**WIFI_PHY_INFO**](ns-wificx-wifi_phy_info.md)