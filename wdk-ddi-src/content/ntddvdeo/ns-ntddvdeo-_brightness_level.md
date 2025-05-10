---
UID: NS:ntddvdeo._BRIGHTNESS_LEVEL
title: BRIGHTNESS_LEVEL (ntddvdeo.h)
description: Contains information about the brightness level.
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
req.typenames: BRIGHTNESS_LEVEL, *PBRIGHTNESS_LEVEL
targetos: Windows
f1_keywords:
 - _BRIGHTNESS_LEVEL
 - ntddvdeo/_BRIGHTNESS_LEVEL
 - PBRIGHTNESS_LEVEL
 - ntddvdeo/PBRIGHTNESS_LEVEL
 - BRIGHTNESS_LEVEL
 - ntddvdeo/BRIGHTNESS_LEVEL
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - _BRIGHTNESS_LEVEL
 - PBRIGHTNESS_LEVEL
 - BRIGHTNESS_LEVEL
---

# BRIGHTNESS_LEVEL structure

## -description

A **BRIGHTNESS_LEVEL** structure contains the brightness levels of a display panel.

## -struct-fields

### -field Count

The number of brightness levels in the array.

### -field Level

Array of brightness levels. The number of elements in this array is specified by the **Count** member.

## - see-also

[**IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES**](ni-ntddvdeo-ioctl_panel_query_brightness_ranges.md)

[**PANEL_QUERY_BRIGHTNESS_RANGES**](ns-ntddvdeo-_panel_query_brightness_ranges.md)
