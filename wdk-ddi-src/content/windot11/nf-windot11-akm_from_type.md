---
UID: NF:windot11.AKM_FROM_TYPE
tech.root: netvista
title: AKM_FROM_TYPE
ms.date: 06/29/2023
targetos: Windows
description: The AKM_FROM_TYPE macro is used to compute the RSNA_AKM_SUITE and WPA_AKM_SUITE enum values.
prerelease: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: windot11.h
req.idl: 
req.include-header: Ndis.h
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
 - windot11.h
api_name:
 - AKM_FROM_TYPE
f1_keywords:
 - AKM_FROM_TYPE
 - windot11/AKM_FROM_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - AKM_FROM_TYPE
---

# AKM_FROM_TYPE function (windot11.h)

## -description

The **AKM_FROM_TYPE** macro is used to compute the [**RSNA_AKM_SUITE**](ne-windot11-rsna_akm_suite.md) and [**WPA_AKM_SUITE**](ne-windot11-wpa_akm_suite.md) enum values.

## -parameters

### -param _prefix

The Robust Secure Network Association (RSNA) Authentication and Key Management (AKM) Organizationally Unique Identifier (OUI) prefix. 

### -param _akm

The AKM type.

## -remarks

## -see-also

[**RSNA_AKM_SUITE**](ne-windot11-rsna_akm_suite.md)

[**WPA_AKM_SUITE**](ne-windot11-wpa_akm_suite.md)

[WiFiCx Wi-Fi 7 feature requirements](/windows-hardware/drivers/netcx/wificx-wi-fi-7)