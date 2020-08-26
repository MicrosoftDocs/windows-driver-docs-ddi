---
UID: NS:d3dkmdt._DXGK_BRIGHTNESS_GET_OUT
title: _DXGK_BRIGHTNESS_GET_OUT (d3dkmdt.h)
description: Contains the output parameters for the DxgkBrightnessGet3 callback function.
ms.assetid: fa213718-aa84-4751-b3a9-767441024a94
ms.date: 10/19/2018
keywords: ["DXGK_BRIGHTNESS_GET_OUT structure"]
f1_keywords:
 - "d3dkmdt/_DXGK_BRIGHTNESS_GET_OUT"
 - "_DXGK_BRIGHTNESS_GET_OUT"
ms.keywords: _DXGK_BRIGHTNESS_GET_OUT, DXGK_BRIGHTNESS_GET_OUT, *PDXGK_BRIGHTNESS_GET_OUT,
req.header: d3dkmdt.h
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
req.typenames: DXGK_BRIGHTNESS_GET_OUT, *PDXGK_BRIGHTNESS_GET_OUT
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- _DXGK_BRIGHTNESS_GET_OUT
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_BRIGHTNESS_GET_OUT structure

## -description

Contains the output parameters for the [DxgkBrightnessGet3](../dispmprt/nc-dispmprt-dxgk_brightness_get_3.md) callback function.

## -struct-fields

### -field CurrentBrightnessMillinits

The current brightness level in millinits of the display.

### -field TargetBrightnessMillinits

The brightness level in millinits that the display is currently transitioning to. If not in a transition, this should equal the current brightness.

