---
UID: NC:sensorscx.PFN_SENSORSCXSENSORCREATE
title: *PFN_SENSORSCXSENSORCREATE
author: windows-driver-content
description: Creates an instance of a sensor in the class extension.
ms.assetid: 5a5df8e4-11e9-4958-b622-64e15bcd8023
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
-	*PFN_SENSORSCXSENSORCREATE
product:
- Windows
targetos: Windows
---

# *PFN_SENSORSCXSENSORCREATE callback function

## -description

Creates an instance of a sensor in the class extension.

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
