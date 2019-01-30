---
UID: NS:d3dkmdt._DXGK_BRIGHTNESS_SENSOR_DATA
title: _DXGK_BRIGHTNESS_SENSOR_DATA (d3dkmdt.h)
description: Describes the sensor data brightness.
ms.assetid: 38aca9c4-ed04-405b-a659-5d5d252a45dc
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGK_BRIGHTNESS_SENSOR_DATA, DXGK_BRIGHTNESS_SENSOR_DATA,
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
req.typenames: DXGK_BRIGHTNESS_SENSOR_DATA
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	_DXGK_BRIGHTNESS_SENSOR_DATA
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_BRIGHTNESS_SENSOR_DATA structure

## -description

Describes the sensor data brightness.

## -struct-fields

### -field Flags

Flags that represent the type of brightness for the sensor data.

### -field Flags.AlsReadingValid

The ALS reading is valid.

### -field Flags.ChromaticityValid

The chromaticity is valid.

### -field Flags.ColorTemperatureValid

The color temperature is valid.

### -field Flags.Reserved

Reserved.

### -field ValidSensorValues

A bitmask that represents which sensor values are valid. The valid flags may change between calls. Not all devices will support all or any of the sensor types.

### -field Size

The size of the structure. Fields for new sensor types will always be added to the end of the structure if it is revised in future updates.

### -field AlsReading

Luminance in lux, measured by an ALS sensor.

### -field Chromaticity

A [DXGK_BRIGHTNESS_SENSOR_DATA_CHROMATICITY](ns-d3dkmdt-_dxgk_brightness_sensor_data_chromaticity.md) structure that contains CIE 1931 chromaticity coordinates from a color sensor.

### -field ColorTemperature

Color temperature in Kelvin, measured by a color sensor.

