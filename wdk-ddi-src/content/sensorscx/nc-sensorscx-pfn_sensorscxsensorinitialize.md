---
UID: NC:sensorscx.PFN_SENSORSCXSENSORINITIALIZE
title: PFN_SENSORSCXSENSORINITIALIZE (sensorscx.h)
description: Sets the enumeration properties of a sensor.
ms.assetid: 43a6c35f-14ef-422d-a5f4-3fd318571a0d
ms.date: 10/19/2018
keywords: ["*PFN_SENSORSCXSENSORINITIALIZE callback function"]
f1_keywords:
 - "sensorscx/*PFN_SENSORSCXSENSORINITIALIZE"
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
- PFN_SENSORSCXSENSORINITIALIZE
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# *PFN_SENSORSCXSENSORINITIALIZE callback function

## -description

Sets the enumeration properties of a sensor. 

## -prototype

```cpp
//Declaration

*PFN_SENSORSCXSENSORINITIALIZE *PfnSensorscxsensorinitialize; 

// Definition

NTSTATUS *PfnSensorscxsensorinitialize 
(
	PSENSORSCX_DRIVER_GLOBALS DriverGlobals
	SENSOROBJECT Sensor
	PSENSOR_CONFIG pSensorConfig
)
{...}

```

## -parameters

### -param DriverGlobals

Global definitions for the driver.

### -param Sensor

A reference to a sensor object.

### -param pSensorConfig

A list of functions that the driver implements. 

## -returns

Returns NTSTATUS.
