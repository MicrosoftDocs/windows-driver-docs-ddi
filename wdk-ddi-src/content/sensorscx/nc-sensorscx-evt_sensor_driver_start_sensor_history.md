---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_START_SENSOR_HISTORY
title: EVT_SENSOR_DRIVER_START_SENSOR_HISTORY (sensorscx.h)
description: Starts recording history in the sensor.
tech.root: sensors
ms.date: 10/19/2018
keywords: ["EVT_SENSOR_DRIVER_START_SENSOR_HISTORY callback function"]
req.header: sensorscx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - EVT_SENSOR_DRIVER_START_SENSOR_HISTORY
 - sensorscx/EVT_SENSOR_DRIVER_START_SENSOR_HISTORY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - sensorscx.h
api_name:
 - EVT_SENSOR_DRIVER_START_SENSOR_HISTORY
---

# EVT_SENSOR_DRIVER_START_SENSOR_HISTORY callback function


## -description

Starts recording history in the sensor.

## -parameters

### -param Sensor

[in] A reference to a sensor object.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

EVT_SENSOR_DRIVER_START_SENSOR_HISTORY EvtSensorDriverStartSensorHistory; 

// Definition

NTSTATUS EvtSensorDriverStartSensorHistory 
(
	SENSOROBJECT Sensor
)
{...}

```

