---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL
title: EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL (sensorscx.h)
description: Cancels history retrieval from the sensor.
tech.root: sensors
ms.date: 10/19/2018
keywords: ["EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL callback function"]
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
 - EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL
 - sensorscx/EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - sensorscx.h
api_name:
 - EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL
---

# EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL callback function


## -description

Cancels history retrieval from the sensor.

## -parameters

### -param Sensor

A reference to the sensor object.

### -param pBytesWritten

Pointer to bytes written.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL EvtSensorDriverCancelHistoryRetrieval; 

// Definition

NTSTATUS EvtSensorDriverCancelHistoryRetrieval 
(
	SENSOROBJECT Sensor
	PULONG pBytesWritten
)
{...}

```

