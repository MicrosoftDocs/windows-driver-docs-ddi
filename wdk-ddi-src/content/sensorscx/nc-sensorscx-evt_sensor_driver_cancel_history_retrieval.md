---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL
title: EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL (sensorscx.h)
description: Cancels history retrieval from the sensor.
ms.assetid: 244e5a2d-1a37-461a-9834-836169158756
ms.date: 10/19/2018
keywords: ["EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL callback function"]
f1_keywords:
 - "sensorscx/EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL"
 - "EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL"
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- sensorscx.h
api_name: 
- EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL callback function

## -description

Cancels history retrieval from the sensor.

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

## -parameters

### -param Sensor

A reference to the sensor object.

### -param pBytesWritten

Pointer to bytes written.

## -returns

Returns NTSTATUS.

