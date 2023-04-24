---
UID: NS:wificx.WIFI_STA_BANDS_COMBINATION
tech.root: netvista
title: WIFI_STA_BANDS_COMBINATION (wificx.h)
ms.date: 09/07/2021
targetos: Windows
description: The WIFI_STA_BANDS_COMBINATION structure contains a list of band IDs that are available for secondary STA connections.
prerelease: false
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
req.target-min-winversvr: 
req.target-type: 
req.typenames: WIFI_STA_BANDS_COMBINATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - WIFI_STA_BANDS_COMBINATION
f1_keywords:
 - WIFI_STA_BANDS_COMBINATION
 - wificx/WIFI_STA_BANDS_COMBINATION
dev_langs:
 - c++
---

## -description

The **WIFI_STA_BANDS_COMBINATION** structure contains a list of band IDs that are available for secondary STA connections.

## -struct-fields

### -field NumStaBands

The number bands.

### -field BandIDs

An array of [**WDI_BAND_ID**](../dot11wificxtypes/ne-dot11wificxtypes-wdi_band_id.md) structures. Currently **MAX_SIMULTANEOUS_BAND_CONNECTIONS_ALLOWED** is defined as follows:

```#define MAX_SIMULTANEOUS_BAND_CONNECTIONS_ALLOWED 4```

## -remarks

## -see-also

[**WIFI_STATION_CAPABILITIES**](ns-wificx-wifi_station_capabilities.md)

