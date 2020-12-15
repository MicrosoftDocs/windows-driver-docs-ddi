---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_ENABLE_WAKE
title: EVT_SENSOR_DRIVER_ENABLE_WAKE (sensorscx.h)
description: Callback to enable wake for the sensor.
old-location: sensors\evt_sensor_driver_enable_wake.htm
tech.root: sensors
ms.date: 05/03/2018
keywords: ["EVT_SENSOR_DRIVER_ENABLE_WAKE callback function"]
ms.keywords: EVT_SENSOR_DRIVER_ENABLE_WAKE, EVT_SENSOR_DRIVER_ENABLE_WAKE callback, EVT_SENSOR_DRIVER_ENABLE_WAKE callback function [Sensor Devices], sensors.evt_sensor_driver_enable_wake, sensorscx/EVT_SENSOR_DRIVER_ENABLE_WAKE
req.header: sensorscx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SENSOR_DRIVER_ENABLE_WAKE
 - sensorscx/EVT_SENSOR_DRIVER_ENABLE_WAKE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - SensorsCx.h
api_name:
 - EVT_SENSOR_DRIVER_ENABLE_WAKE
---

# EVT_SENSOR_DRIVER_ENABLE_WAKE callback function


## -description

Callback to enable wake for the sensor.

## -parameters

### -param Sensor 

[in] A reference to the sensor object.

## -returns

This function returns STATUS_SUCCESS when completed successfully.

<div class="alert"><b>Note</b>  The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.</div>
<div> </div>

## -remarks

This DDSI function does not compulsorily have to be implemented by the driver because it is expected that some sensor drivers do not care about enabling wake on the sensor. If it not implemented the enable call is ignored and a STATUS_SUCCESS is returned. This is primarily because PKEY_Sensor_WakeCapable is implemented today and used by some sensors such as the accelerometer and the proximity sensor, and for backward compatibility, implementing this DDSI is optional.

