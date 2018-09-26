---
UID: NC:sensorscx.PFN_SENSORSCXSTATECHANGE
title: *PFN_SENSORSCXSTATECHANGE
author: windows-driver-content
description: Used to initialize a sensor state change.
ms.assetid: 7c918334-c20f-4edd-988b-4bbe8bc2c9d8
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	*PFN_SENSORSCXSTATECHANGE
product:
- Windows
targetos: Windows
---

# *PFN_SENSORSCXSTATECHANGE callback function

## -description

Used to initialize a sensor state change. 

## -prototype

```
//Declaration

*PFN_SENSORSCXSTATECHANGE *PfnSensorscxstatechange; 

// Definition

VOID *PfnSensorscxstatechange 
(
	PSENSORSCX_DRIVER_GLOBALS DriverGlobals
	SENSOROBJECT Sensor
	SENSOR_STATE State
)
{...}

```

## -parameters

### -param DriverGlobals

Global definitions for the driver.

### -param Sensor

A reference to a sensor object.

### -param State

The state of the sensor.

## -returns

Returns VOID.