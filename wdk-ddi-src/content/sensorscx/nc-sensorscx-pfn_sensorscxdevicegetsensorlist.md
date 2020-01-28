---
UID: NC:sensorscx.PFN_SENSORSCXDEVICEGETSENSORLIST
title: PFN_SENSORSCXDEVICEGETSENSORLIST (sensorscx.h)
description: Returns a list of sensor instances associated with a WDFDEVICE.
ms.assetid: aec04f70-2160-4990-bf64-ac7f4a4fc838
ms.date: 10/19/2018
f1_keywords:
 - "sensorscx/*PFN_SENSORSCXDEVICEGETSENSORLIST"
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
- *PFN_SENSORSCXDEVICEGETSENSORLIST
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# *PFN_SENSORSCXDEVICEGETSENSORLIST callback function

## -description

Returns a list of sensor instances associated with a WDFDEVICE.

## -prototype

```cpp
//Declaration

*PFN_SENSORSCXDEVICEGETSENSORLIST *PfnSensorscxdevicegetsensorlist; 

// Definition

NTSTATUS *PfnSensorscxdevicegetsensorlist 
(
	PSENSORSCX_DRIVER_GLOBALS DriverGlobals
	WDFDEVICE FxDevice
	SENSOROBJECT *pSensorList
	PULONG pListCount
)
{...}

```

## -parameters

### -param DriverGlobals

Global definitions for the driver.

### -param FxDevice

A WDFDEVICE handle to the framework device object that represents the sensor.

### -param *pSensorList

A list of sensor instances.

### -param pListCount

The number of SENSOROBJECTS in *pSensorList*.

## -returns

Returns NTSTATUS with different values. Some values that may be returned are the following:

* STATUS_SUCCESS is returned if the function completes successfully. 
* STATUS_INVALID_PARAMETER is returned if any of the In parameters are NULL. 
* STATUS_NOT_FOUND is returned if the controller is not available from the FxDevice. 

## -remarks



## -see-also
