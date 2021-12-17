---
UID: NC:sensorscx.PFN_SENSORSCXSENSORDATAREADY
title: PFN_SENSORSCXSENSORDATAREADY (sensorscx.h)
description: Notifies the class extension that the driver has retrieved data.
tech.root: sensors
ms.date: 12/16/2021
keywords: ["*PFN_SENSORSCXSENSORDATAREADY callback function"]
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
 - PFN_SENSORSCXSENSORDATAREADY
 - sensorscx/PFN_SENSORSCXSENSORDATAREADY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - sensorscx.h
api_name:
 - PFN_SENSORSCXSENSORDATAREADY
---

# *PFN_SENSORSCXSENSORDATAREADY callback function

## -description

Notifies the class extension that the driver has retrieved data.

## -parameters

### -param DriverGlobals

Global definitions for the driver.

### -param Sensor

A reference to a sensor object.

### -param pSensorData

Pointer to a list of sensor properties.

## -prototype

```cpp
//Declaration

*PFN_SENSORSCXSENSORDATAREADY *PfnSensorscxsensordataready; 

// Definition

VOID *PfnSensorscxsensordataready 
(
  PSENSORSCX_DRIVER_GLOBALS DriverGlobals
  SENSOROBJECT Sensor
  PSENSOR_COLLECTION_LIST pSensorData
)
{...}

```

## -returns

This function returns an **NTSTATUS** with different values. Some values that may be returned are:

- STATUS_SUCCESS is returned if the function completes successfully.
- STATUS_UNSUCCESSFUL is returned if the function does not complete successfully.
- STATUS_INVALID_PARAMETER is returned if any of the _In_ parameters are NULL.

> [!NOTE]
> Any client that calls **SensorsCxSensorDataReady** must make sure that **SensorsCxSensorDataReady** is started, before the call is made. Calling **SensorsCxSensorDataReady** before it is started can cause the sensor class extension to become unresponsive.
