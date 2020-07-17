---
UID: NC:sensorscx.PFN_SENSORSCXSENSORDATAREADY
title: PFN_SENSORSCXSENSORDATAREADY (sensorscx.h)
description: Notifies the class extension that the driver has retrieved data.
ms.assetid: 3f3740d2-5c45-483f-9ed4-5d4b65726705
ms.date: 10/19/2018
keywords: ["*PFN_SENSORSCXSENSORDATAREADY callback function"]
f1_keywords:
 - "sensorscx/*PFN_SENSORSCXSENSORDATAREADY"
 - "*PFN_SENSORSCXSENSORDATAREADY"
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
- PFN_SENSORSCXSENSORDATAREADY
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# *PFN_SENSORSCXSENSORDATAREADY callback function

## -description

Notifies the class extension that the driver has retrieved data. 

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

## -parameters

### -param DriverGlobals

Global definitions for the driver.

### -param Sensor

A reference to a sensor object.

### -param pSensorData: 

Pointer to a list of sensor properties.

