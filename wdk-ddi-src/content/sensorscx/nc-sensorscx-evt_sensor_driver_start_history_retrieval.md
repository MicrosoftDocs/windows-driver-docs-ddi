---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_START_HISTORY_RETRIEVAL
title: EVT_SENSOR_DRIVER_START_HISTORY_RETRIEVAL (sensorscx.h)
description: Starts retrieving the history recorded so far in the sensor.
ms.assetid: 97eccb93-e184-4350-a47e-2072bf368893
ms.date: 10/19/2018
keywords: ["EVT_SENSOR_DRIVER_START_HISTORY_RETRIEVAL callback function"]
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
 - EVT_SENSOR_DRIVER_START_HISTORY_RETRIEVAL
 - sensorscx/EVT_SENSOR_DRIVER_START_HISTORY_RETRIEVAL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - sensorscx.h
api_name:
 - EVT_SENSOR_DRIVER_START_HISTORY_RETRIEVAL
---

# EVT_SENSOR_DRIVER_START_HISTORY_RETRIEVAL callback function


## -description

Starts retrieving the history recorded so far in the sensor.

## -parameters

### -param Sensor

[in] A reference to a sensor object.

### -param pHistory

[in, out] Pointer to the sensor collection list.

### -param HistorySizeInBytes

[in] The size of the *pHistory*, in bytes.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

EVT_SENSOR_DRIVER_START_HISTORY_RETRIEVAL EvtSensorDriverStartHistoryRetrieval; 

// Definition

NTSTATUS EvtSensorDriverStartHistoryRetrieval 
(
	SENSOROBJECT Sensor
	PSENSOR_COLLECTION_LIST pHistory
	ULONG HistorySizeInBytes
)
{...}

```

