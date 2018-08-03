---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_DISABLE_WAKE
title: EVT_SENSOR_DRIVER_DISABLE_WAKE
author: windows-driver-content
description: Callback to disable wake for the sensor.
old-location: sensors\evt_sensor_driver_disable_wake.htm
tech.root: sensors
ms.assetid: 15873D33-1423-47D7-8CE6-F2012241B658
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: EVT_SENSOR_DRIVER_DISABLE_WAKE, EVT_SENSOR_DRIVER_DISABLE_WAKE callback, EVT_SENSOR_DRIVER_DISABLE_WAKE callback function [Sensor Devices], sensors.evt_sensor_driver_disable_wake, sensorscx/EVT_SENSOR_DRIVER_DISABLE_WAKE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "_requires_same_"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	SensorsCx.h
api_name:
-	EVT_SENSOR_DRIVER_DISABLE_WAKE
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SENSOR_DRIVER_DISABLE_WAKE callback function


## -description


Callback to disable wake for the sensor.


## -parameters




### -param Sensor

A reference to the sensor object.


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<div class="alert"><b>Note</b>  The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.</div>
<div> </div>



## -remarks



This DDSI function does not compulsorily have to be implemented by the driver because it is expected that some sensor drivers do not care about disabling wake on the sensor. If it not implemented the enable call is ignored and a STATUS_SUCCESS is returned. This is primarily because PKEY_Sensor_WakeCapable is implemented today and used by some sensors such as the accelerometer and the proximity sensor, and for backward compatibility, implementing this DDSI is optional.



