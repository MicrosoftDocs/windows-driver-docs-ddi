---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_DEVICE_IO_CONTROL
title: EVT_SENSOR_DRIVER_DEVICE_IO_CONTROL
author: windows-driver-content
description: Callback to handle IOCTL.
ms.assetid: 293854c7-882b-42dd-b4ef-cb19d0366e8d
ms.date: 10/19/2018
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
-	EVT_SENSOR_DRIVER_DEVICE_IO_CONTROL
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_SENSOR_DRIVER_DEVICE_IO_CONTROL callback function

## -description

Callback to handle IOCTL.

## -prototype

```cpp
//Declaration

EVT_SENSOR_DRIVER_DEVICE_IO_CONTROL EvtSensorDriverDeviceIoControl; 

// Definition

NTSTATUS EvtSensorDriverDeviceIoControl 
(
	SENSOROBJECT Sensor
	WDFREQUEST Request
	size_t OutputBufferLength
	size_t InputBufferLength
	ULONG IoControlCode
)
{...}

```

## -parameters

### -param Sensor

A reference to the sensor object.

### -param Request

The I/O request.

### -param OutputBufferLength

The output buffer length.

### -param InputBufferLength

The input buffer length.

### -param IoControlCode

The I/O control code.

## -returns

Returns NTSTATUS.
