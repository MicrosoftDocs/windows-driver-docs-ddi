---
UID: NS:d3dkmdt._DXGK_BRIGHTNESS_SET_IN
title: _DXGK_BRIGHTNESS_SET_IN (d3dkmdt.h)
description:
ms.assetid: c19ab02a-7216-4a94-8d8c-832bdcf22c02
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmdt/_DXGK_BRIGHTNESS_SET_IN"
ms.keywords: _DXGK_BRIGHTNESS_SET_IN, *PDXGK_BRIGHTNESS_SET_IN, DXGK_BRIGHTNESS_SET_IN,
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
req.typenames: DXGK_BRIGHTNESS_SET_IN, *PDXGK_BRIGHTNESS_SET_IN
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- _DXGK_BRIGHTNESS_SET_IN
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_BRIGHTNESS_SET_IN structure

## -description

Contains input parameters for the [DxgkBrightnessSet3](../dispmprt/nc-dispmprt-dxgk_brightness_set_3.md) callback function.

## -struct-fields

### -field BrightnessMillinits

The brightness level in millinits to transition to. If the driver has not set [DXGK_BRIGHTNESS_CAPS.NitsBrightness](ns-d3dkmdt-_dxgk_brightness_caps.md), then this value means the brightness level in uncalibrated thousandths of a percent.

For example, if <b>BrightnessMillinits</b> is set to 60500 and <b>NitsBrightness</b> is set, this means 60.5 nits luminance. If <b>NitsBrightness</b> is not set, this means 60.5%.

### -field TransitionTimeMs

How long the transition should take in milliseconds.

### -field SensorReadings

A [DXGK_BRIGHTNESS_SENSOR_DATA](ns-d3dkmdt-_dxgk_brightness_sensor_data.md) structure that contains sensor readings the driver can use to determine the best way to achieve the desired brightness under current lighting conditions. Not all devices will support all or any sensor readings, and the driver should not fail if any are missing.
