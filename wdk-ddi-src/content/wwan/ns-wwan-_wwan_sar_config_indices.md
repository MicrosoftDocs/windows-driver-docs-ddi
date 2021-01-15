---
UID: NS:wwan._WWAN_SAR_CONFIG_INDICES
title: _WWAN_SAR_CONFIG_INDICES (wwan.h)
description: The WWAN_SAR_CONFIG_INDICES structure represents a Specific Absorption Rate (SAR) configuration for a mobile broadband (MBB) modem.
tech.root: netvista
ms.date: 08/20/2018
keywords: ["WWAN_SAR_CONFIG_INDICES structure"]
ms.keywords: _WWAN_SAR_CONFIG_INDICES, WWAN_SAR_CONFIG_INDICES, *PWWAN_SAR_CONFIG_INDICES,
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
req.typenames: WWAN_SAR_CONFIG_INDICES, *PWWAN_SAR_CONFIG_INDICES
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _WWAN_SAR_CONFIG_INDICES
 - wwan/_WWAN_SAR_CONFIG_INDICES
 - PWWAN_SAR_CONFIG_INDICES
 - wwan/PWWAN_SAR_CONFIG_INDICES
 - WWAN_SAR_CONFIG_INDICES
 - wwan/WWAN_SAR_CONFIG_INDICES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SAR_CONFIG_INDICES
 - PWWAN_SAR_CONFIG_INDICES
 - WWAN_SAR_CONFIG_INDICES
---

# _WWAN_SAR_CONFIG_INDICES structure


## -description

The **WWAN_SAR_CONFIG_INDICES** structure represents a Specific Absorption Rate (SAR) configuration for a mobile broadband (MBB) modem.

## -struct-fields

### -field SarAntennaIndex

A **ULONG** value specifying the antenna, or executor, for this SAR configuration.

### -field SarBackoffIndex

A **ULONG** value specifying the SAR back off index for the antenna indicated by **SarAntennaIndex**.

## -remarks

A list of **WWAN_SAR_CONFIG_INDICES** follows the **SarConfigIndexListHeader** member of either the [**WWAN_SET_SAR_CONFIG**](ns-wwan-_wwan_set_sar_config.md) structure or the [**WWAN_SAR_CONFIG_INFO**](ns-wwan-_wwan_sar_config_info.md) structure.

## -see-also

[**WWAN_SET_SAR_CONFIG**](ns-wwan-_wwan_set_sar_config.md)

[**WWAN_SAR_CONFIG_INFO**](ns-wwan-_wwan_sar_config_info.md)

