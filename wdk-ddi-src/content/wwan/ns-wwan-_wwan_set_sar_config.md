---
UID: NS:wwan._WWAN_SET_SAR_CONFIG
title: _WWAN_SET_SAR_CONFIG (wwan.h)
description: The WWAN_SET_SAR_CONFIG structure describes Specific Absorption Rate (SAR) information that a mobile broadband (MB) modem should use to set its SAR configuration.
tech.root: netvista
ms.assetid: a4703e73-677a-42ea-8f8b-dbd77957ef6e
ms.date: 08/20/2018
ms.topic: struct
ms.keywords: _WWAN_SET_SAR_CONFIG, WWAN_SET_SAR_CONFIG, *PWWAN_SET_SAR_CONFIG, 
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
req.typenames: WWAN_SET_SAR_CONFIG, *PWWAN_SET_SAR_CONFIG
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_SET_SAR_CONFIG
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_SET_SAR_CONFIG structure

## -description

The **WWAN_SET_SAR_CONFIG** structure describes Specific Absorption Rate (SAR) information that a mobile broadband (MB) modem should use to set its SAR configuration.

## -struct-fields

### -field SarMode

A [**WWAN_SAR_CONTROL_MODE**](ne-wwan-_wwan_sar_control_mode.md) value that specifies how the SAR back off mechanism should be controlled.
 
### -field SarBackoffStatus

A [**WWAN_SAR_BACKOFF_STATE**](ne-wwan-_wwan_sar_backoff_state.md) value that specifies the state of SAR backoff for the modem's antennas.
 
### -field SarConfigIndexListHeader
 
A [**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md) structure that represents a list of SAR configurations that the modem supports. The **ElementType** member in the **WWAN_LIST_HEADER** should be set to **WwanStructSarConfig**. The **ElementCount** member in the **WWAN_LIST_HEADER** should be set to the number of SAR configurations that follow the **WWAN_LIST_HEADER** structure.

## -remarks

This structure is used in the [**NDIS_WWAN_SET_SAR_CONFIG**](../ndiswwan/ns-ndiswwan-_ndis_wwan_set_sar_config.md) structure.

## -see-also

[MB SAR Platform Support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-sar-platform-support)

[OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config)

[**NDIS_WWAN_SET_SAR_CONFIG**](../ndiswwan/ns-ndiswwan-_ndis_wwan_set_sar_config.md)

[**WWAN_SAR_CONTROL_MODE**](ne-wwan-_wwan_sar_control_mode.md)

[**WWAN_SAR_BACKOFF_STATE**](ne-wwan-_wwan_sar_backoff_state.md)

[**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md)
