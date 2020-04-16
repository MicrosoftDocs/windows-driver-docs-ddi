---
UID: NS:ntddvdeo._PANEL_BRIGHTNESS_SENSOR_DATA
title: _PANEL_BRIGHTNESS_SENSOR_DATA (ntddvdeo.h)
description: Used to set the level of optimization to control the brightness of a panel.
tech.root: display
ms.assetid: 228da293-6f46-4a8f-b916-0e3e9baaf237
ms.date: 10/19/2018
keywords: ["_PANEL_BRIGHTNESS_SENSOR_DATA structure"]
f1_keywords:
 - "ntddvdeo/_PANEL_BRIGHTNESS_SENSOR_DATA"
ms.keywords: _PANEL_BRIGHTNESS_SENSOR_DATA, PANEL_BRIGHTNESS_SENSOR_DATA,
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
req.typenames: PANEL_BRIGHTNESS_SENSOR_DATA
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- ntddvdeo.h
api_name:
- _PANEL_BRIGHTNESS_SENSOR_DATA
product: 
- Windows
targetos: Windows
---

# _PANEL_BRIGHTNESS_SENSOR_DATA structure

## -description

Used to set the level of optimization to control the brightness of a panel.

## -struct-fields

### -field AlsReadingValid

Not all devices will support all or any of the sensor types. This is a bitmask representing which sensor values are valid. The valid flags may change between calls.

### -field ChromaticityCoordinateValid

Indicates whether the chromaticity coordinate is valid.

### -field ColorTemperatureValid

Indicates whether the color temperature is valid.

### -field Reserved

Reserved.

### -field Value

Value of the brightness sensor data.

### -field AlsReading

Sensor readings the driver can use to determine the best way to achieve the desired brightness under current lighting conditions. Not all devices will support all or any sensor readings, and the driver should not fail if any are missing.

### -field ChromaticityCoordinate

The chromaticity coordinates from a color sensor.

### -field ColorTemperature

Color temperature in Kelvin, measured by a color sensor.

