---
UID: NS:wwan._WWAN_SAR_CONFIG_INFO
title: _WWAN_SAR_CONFIG_INFO (wwan.h)
description: The WWAN_SAR_CONFIG_INFO structure describes a modem's current Specific Absorption Rate (SAR) configuration information.
tech.root: netvista
ms.assetid: 465fb01d-bc43-4e03-8039-304ceb53bb7d
ms.date: 08/20/2018
ms.topic: struct
f1_keywords:
 - "wwan/_WWAN_SAR_CONFIG_INFO"
ms.keywords: _WWAN_SAR_CONFIG_INFO, WWAN_SAR_CONFIG_INFO, *PWWAN_SAR_CONFIG_INFO, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: WWAN_SAR_CONFIG_INFO, *PWWAN_SAR_CONFIG_INFO
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_SAR_CONFIG_INFO
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_SAR_CONFIG_INFO structure

## -description

The **WWAN_SAR_CONFIG_INFO** structure describes a modem's current Specific Absorption Rate (SAR) configuration information.

## -struct-fields

### -field SarMode

A [**WWAN_SAR_CONTROL_MODE**](ne-wwan-_wwan_sar_control_mode.md) value that specifies how the SAR back off mechanism is controlled.
 
### -field SarBackoffStatus

A [**WWAN_SAR_BACKOFF_STATE**](ne-wwan-_wwan_sar_backoff_state.md) value that specifies the state of SAR backoff for the modem's antennas.
 
### -field SarWifiIntegration

A [**WWAN_SAR_WIFI_HARDWARE_INTEGRATION**](ne-wwan-_wwan_sar_wifi_hardware_integration.md) value that specifies whether Wi-Fi and Cellular are integrated at the hardware level.
 
### -field SarConfigIndexListHeader

A [**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md) structure that represents a list of SAR configurations that the modem supports. The **ElementType** member in the **WWAN_LIST_HEADER** should be set to **WwanStructSarConfig**. The **ElementCount** member in the **WWAN_LIST_HEADER** should be set to the number of [**WWAN_SAR_CONFIG_INDICES**](ns-wwan-_wwan_sar_config_indices.md) structures that follow the **WWAN_LIST_HEADER** structure.

## -remarks

This structure is used in the [**NDIS_WWAN_SAR_CONFIG_INFO**](../ndiswwan/ns-ndiswwan-_ndis_wwan_sar_config_info.md) structure.

## -see-also

[MB SAR Platform Support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-sar-platform-support)

[OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config)

[**NDIS_WWAN_SAR_CONFIG_INFO**](../ndiswwan/ns-ndiswwan-_ndis_wwan_sar_config_info.md)

[**WWAN_SAR_CONTROL_MODE**](ne-wwan-_wwan_sar_control_mode.md)

[**WWAN_SAR_BACKOFF_STATE**](ne-wwan-_wwan_sar_backoff_state.md)

[**WWAN_SAR_WIFI_HARDWARE_INTEGRATION**](ne-wwan-_wwan_sar_wifi_hardware_integration.md)

[**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md)
