---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_STOP_SENSOR
title: EVT_SENSOR_DRIVER_STOP_SENSOR
author: windows-driver-content
description: This callback function stops the sensor.
old-location: sensors\evtsensorstop.htm
old-project: sensors
ms.assetid: 25F57CA6-09A0-438B-8866-9F9DC01B5388
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EVT_SENSOR_DRIVER_STOP_SENSOR, EvtSensorStop, EvtSensorStop callback function [Sensor Devices], sensors.evtsensorstop, sensorscx/EvtSensorStop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	SensorsCx.h
apiname:
-	EvtSensorStop
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_STOP_SENSOR callback


## -description


This callback function stops the sensor.


## -prototype


````
NT_STATUS EvtSensorStop(
   SENSOROBJECT Sensor
);
````


## -parameters




### -param Sensor

A reference to a sensor object.


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -remarks



This function must be implemented by the driver and is called by the class extension.



