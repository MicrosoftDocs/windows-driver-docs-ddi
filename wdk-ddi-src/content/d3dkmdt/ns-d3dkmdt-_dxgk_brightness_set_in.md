---
UID: NS:d3dkmdt._DXGK_BRIGHTNESS_SET_IN
title: _DXGK_BRIGHTNESS_SET_IN
author: windows-driver-content
description:
ms.assetid: c19ab02a-7216-4a94-8d8c-832bdcf22c02
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.typenames: *PDXGK_BRIGHTNESS_SET_IN, DXGK_BRIGHTNESS_SET_IN
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	_DXGK_BRIGHTNESS_SET_IN
product: Windows
targetos: Windows
---

# _DXGK_BRIGHTNESS_SET_IN structure

## -description

Contains input parameters for the [DxgkBrightnessSet3](..\dispmprt\nc-dispmprt-dxgk_brightness_set_3.md) callback function.

## -struct-fields

### -field BrightnessMillinits

The brightness level in millinits to transition to.

### -field TransitionTimeMs

How long the transition should take.

### -field SensorReadings

A [DXGK_BRIGHTNESS_SENSOR_DATA](ns-d3dkmdt-_dxgk_brightness_sensor_data.md) structure that contains sensor readings the driver can use to determine the best way to achieve the desired brightness under current lighting conditions. Not all devices will support all or any sensor readings, and the driver should not fail if any are missing.
