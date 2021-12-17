---
UID: NC:sensorscx.PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED
title: PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED (sensorscx.h)
description: Indicates that the history retrieval has completed.
tech.root: sensors
ms.date: 12/16/2021
keywords: ["*PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED callback function"]
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
 - PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED
 - sensorscx/PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - sensorscx.h
api_name:
 - PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED
---

# *PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED callback function

## -description

Indicates that the history retrieval has completed.

## -parameters

### -param DriverGlobals [in]

Global definitions for the driver.

### -param Sensor [in]

A reference to a sensor object.

### -param BytesWritten [in]

The number of bytes written to the sensor object's history.

### -param InStatus [in]

The current status of the sensor object.

## -prototype

```cpp
//Declaration

*PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED *PfnSensorscxsensorhistoryretrievalcompleted; 

// Definition

VOID *PfnSensorscxsensorhistoryretrievalcompleted 
(
  PSENSORSCX_DRIVER_GLOBALS DriverGlobals
  SENSOROBJECT Sensor
  ULONG BytesWritten
  NTSTATUS InStatus
)
{...}

```

## -returns

This function returns an **NTSTATUS** with different values. Some values that may be returned are:

- STATUS_SUCCESS is returned if the function completes successfully.
- STATUS_UNSUCCESSFUL is returned if the function does not complete successfully.
- STATUS_INVALID_PARAMETER is returned if any of the \_In\_ parameters are NULL.
