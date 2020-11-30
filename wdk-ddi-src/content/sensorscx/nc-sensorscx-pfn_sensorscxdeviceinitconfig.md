---
UID: NC:sensorscx.PFN_SENSORSCXDEVICEINITCONFIG
title: PFN_SENSORSCXDEVICEINITCONFIG (sensorscx.h)
description: Configures the sensor device.
tech.root: sensors
ms.assetid: 995a8d23-3a2c-4c7a-9b53-118c6ef0e403
ms.date: 10/19/2018
keywords: ["*PFN_SENSORSCXDEVICEINITCONFIG callback function"]
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
 - PFN_SENSORSCXDEVICEINITCONFIG
 - sensorscx/PFN_SENSORSCXDEVICEINITCONFIG
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - sensorscx.h
api_name:
 - PFN_SENSORSCXDEVICEINITCONFIG
---

# *PFN_SENSORSCXDEVICEINITCONFIG callback function


## -description

Configures the sensor device.

## -parameters

### -param DriverGlobals

Global definitions for the driver.

### -param pFxDeviceInit

A reference to WDFDEVICE_INIT.

### -param pFdoAttributes

A reference to WDF_OBJECT_ATTRIBUTES.

### -param Flags

The flags for the sensor driver. Reserved set to 0.

## -returns

This function returns STATUS_SUCCESS when completed successfully. When an invalid parameter is supplied or this function fails, STATUS_INVALID_PARAMETER is returned. This function can also return other NTSTATUS values.

## -prototype

```cpp
//Declaration

*PFN_SENSORSCXDEVICEINITCONFIG *PfnSensorscxdeviceinitconfig; 

// Definition

NTSTATUS *PfnSensorscxdeviceinitconfig 
(
	PSENSORSCX_DRIVER_GLOBALS DriverGlobals
	PWDFDEVICE_INIT pFxDeviceInit
	PWDF_OBJECT_ATTRIBUTES pFdoAttributes
	ULONG Flags
)
{...}

```

