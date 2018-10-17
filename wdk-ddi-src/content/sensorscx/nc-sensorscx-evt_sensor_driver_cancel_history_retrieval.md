---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL
title: EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL
author: windows-driver-content
description: Cancels history retrieval from the sensor.
ms.assetid: 244e5a2d-1a37-461a-9834-836169158756
ms.date: 
ms.topic: callback
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	sensorscx.h
api_name: 
-	EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL
product:
- Windows
targetos: Windows
---

# EVT_SENSOR_DRIVER_CANCEL_HISTORY_RETRIEVAL callback function

## -description

Cancels history retrieval from the sensor.

## -prototype

```
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

