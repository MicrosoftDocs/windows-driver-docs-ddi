---
UID: NS:ntddvdeo._PANEL_QUERY_BRIGHTNESS_RANGES
title: _PANEL_QUERY_BRIGHTNESS_RANGES (ntddvdeo.h)
description: Queries a list of supported nit ranges.
tech.root: display
ms.date: 10/19/2018
keywords: ["PANEL_QUERY_BRIGHTNESS_RANGES structure"]
ms.keywords: _PANEL_QUERY_BRIGHTNESS_RANGES, PANEL_QUERY_BRIGHTNESS_RANGES, *PPANEL_QUERY_BRIGHTNESS_RANGES,
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

# _PANEL_QUERY_BRIGHTNESS_RANGES structure


## -description

Queries a list of supported nit ranges.

## -struct-fields

### -field BrightnessLevel

The level of brightness.

### -field NitRanges

A list of supported nit ranges of the display panel.

### -field Version

The target version. This value should always be DXGK_BRIGHTNESS_INTERFACE_VERSION_3.

