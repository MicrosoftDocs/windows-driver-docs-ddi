---
UID: NS:ntddvdeo._PANEL_QUERY_BRIGHTNESS_RANGES
title: PANEL_QUERY_BRIGHTNESS_RANGES (ntddvdeo.h)
description: Queries a list of supported nit ranges.
tech.root: display
ms.date: 05/09/2025
req.header: ntddvdeo.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: PANEL_QUERY_BRIGHTNESS_RANGES, *PPANEL_QUERY_BRIGHTNESS_RANGES
targetos: Windows
f1_keywords:
 - _PANEL_QUERY_BRIGHTNESS_RANGES
 - ntddvdeo/_PANEL_QUERY_BRIGHTNESS_RANGES
 - PPANEL_QUERY_BRIGHTNESS_RANGES
 - ntddvdeo/PPANEL_QUERY_BRIGHTNESS_RANGES
 - PANEL_QUERY_BRIGHTNESS_RANGES
 - ntddvdeo/PANEL_QUERY_BRIGHTNESS_RANGES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - _PANEL_QUERY_BRIGHTNESS_RANGES
 - PPANEL_QUERY_BRIGHTNESS_RANGES
 - PANEL_QUERY_BRIGHTNESS_RANGES
---

# PANEL_QUERY_BRIGHTNESS_RANGES structure

## -description

The **PANEL_QUERY_BRIGHTNESS_RANGES** structure contains a list of supported nit ranges.

## -struct-fields

### -field Version

a [**BRIGHTNESS_INTERFACE_VERSION**](ne-ntddvdeo-_brightness_interface_version.md) value that specifies the target interface version. This value should always be DXGK_BRIGHTNESS_INTERFACE_VERSION_3.

### -field BrightnessLevel

A [**BRIGHTNESS_LEVEL**](ns-ntddvdeo-_brightness_level.md) structure for the list of supported brightness levels of the display panel.

### -field NitRanges

A [**BRIGHTNESS_NIT_RANGE**](ns-ntddvdeo-_brightness_nit_range.md) structure for the supported nit ranges of the display panel.

## - see-also

[**IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES**](ni-ntddvdeo-ioctl_panel_query_brightness_ranges.md)
