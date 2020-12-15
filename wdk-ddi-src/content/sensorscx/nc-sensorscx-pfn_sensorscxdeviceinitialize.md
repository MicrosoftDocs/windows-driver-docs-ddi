---
UID: NC:sensorscx.PFN_SENSORSCXDEVICEINITIALIZE
title: PFN_SENSORSCXDEVICEINITIALIZE (sensorscx.h)
description: Initializes the sensor in the class extension.
tech.root: sensors
ms.date: 10/19/2018
keywords: ["*PFN_SENSORSCXDEVICEINITIALIZE callback function"]
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
 - PFN_SENSORSCXDEVICEINITIALIZE
 - sensorscx/PFN_SENSORSCXDEVICEINITIALIZE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - sensorscx.h
api_name:
 - PFN_SENSORSCXDEVICEINITIALIZE
---

# *PFN_SENSORSCXDEVICEINITIALIZE callback function


## -description

Initializes the sensor in the class extension.

## -parameters

### -param DriverGlobals

Global definitions for the driver.

### -param FxDevice

A WDFDEVICE handle to the framework device object that represents the sensor.

### -param pSensorConfig

A list of functions that the driver implements.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

*PFN_SENSORSCXDEVICEINITIALIZE *PfnSensorscxdeviceinitialize; 

// Definition

NTSTATUS *PfnSensorscxdeviceinitialize 
(
	PSENSORSCX_DRIVER_GLOBALS DriverGlobals
	WDFDEVICE FxDevice
	PSENSOR_CONTROLLER_CONFIG pSensorConfig
)
{...}

```

