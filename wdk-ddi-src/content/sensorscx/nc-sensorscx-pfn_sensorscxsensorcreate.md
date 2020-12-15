---
UID: NC:sensorscx.PFN_SENSORSCXSENSORCREATE
title: PFN_SENSORSCXSENSORCREATE (sensorscx.h)
description: Creates an instance of a sensor in the class extension.
tech.root: sensors
ms.date: 10/19/2018
keywords: ["*PFN_SENSORSCXSENSORCREATE callback function"]
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
 - PFN_SENSORSCXSENSORCREATE
 - sensorscx/PFN_SENSORSCXSENSORCREATE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - sensorscx.h
api_name:
 - PFN_SENSORSCXSENSORCREATE
---

# *PFN_SENSORSCXSENSORCREATE callback function


## -description

Creates an instance of a sensor in the class extension.

## -parameters

### -param DriverGlobals

Global definitions for the driver.

### -param FxDevice

A WDFDEVICE handle to the framework device object that represents the sensor.

### -param pSensorAttributes

A reference to sensor attributes, in WDF_OBJECT_ATTRIBUTES.

### -param pSensor

A reference to a sensor object.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

*PFN_SENSORSCXSENSORCREATE *PfnSensorscxsensorcreate; 

// Definition

NTSTATUS *PfnSensorscxsensorcreate 
(
	PSENSORSCX_DRIVER_GLOBALS DriverGlobals
	WDFDEVICE FxDevice
	PWDF_OBJECT_ATTRIBUTES pSensorAttributes
	PSENSOROBJECT pSensor
)
{...}

```

