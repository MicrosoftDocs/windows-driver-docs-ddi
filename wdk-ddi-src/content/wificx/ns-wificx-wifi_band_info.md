---
UID: NS:wificx._WIFI_BAND_INFO
tech.root: netvista
<<<<<<< HEAD
title: WIFI_BAND_INFO (wificx.h)
ms.date: 08/26/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_BAND_INFO structure contains band information. 
=======
title: WIFI_BAND_INFO
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WIFI_BAND_INFO structure for internal use only. Don't use this structure in your code."
>>>>>>> main
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11
>>>>>>> main
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_BAND_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_BAND_INFO
 - WIFI_BAND_INFO
f1_keywords:
 - _WIFI_BAND_INFO
 - wificx/_WIFI_BAND_INFO
 - WIFI_BAND_INFO
 - wificx/WIFI_BAND_INFO
dev_langs:
 - c++
---

## -description

The **WIFI_BAND_INFO** structure contains band information. 

## -struct-fields

### -field BandID

A [**WDI_BAND_ID**](../dot11wificxtypes/ne-dot11wificxtypes-wdi_band_id.md) structure that represents this band ID.

### -field BandState9

Specifies whether this band is enabled or not.

### -field NumValidPhyTypes

The number of valid PHY types in this band.

### -field ValidPhyTypeList

A pointer to a list of valid PHY types in this band, defined by the [**WDI_PHY_TYPE**](../dot11wificxtypes/ne-dot11wificxtypes-wdi_phy_type.md) enum.

### -field NumValidChannelTypes

The number of valid channel types in this band.

### -field ValidChannelTypes

A pointer to a list of valid channel numbers in this band formatted as [**WDI_CHANNEL_MAPPING_ENTRY**](../dot11wificxtypes/ns-dot11wificxtypes-wdi_channel_mapping_entry.md) structures.

### -field NumChannelWidths

The number of channel widths.

### -field ChannelWidthList

A pointer to a list of channel widths in MHz.

## -remarks

**WIFI_BAND_INFO** is a member of the [**WIFI_BAND_CAPABILITIES**](ns-wificx-wifi_band_capabilities.md) structure.

## -see-also

[**WIFI_BAND_CAPABILITIES**](ns-wificx-wifi_band_capabilities.md)