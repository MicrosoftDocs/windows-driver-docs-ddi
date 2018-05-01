---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_START_SENSOR
title: EVT_SENSOR_DRIVER_START_SENSOR
author: windows-driver-content
description: This callback function starts the sensor based on the default properties specified by the driver, or properties set by the class extension.
old-location: sensors\evtsensorstart.htm
old-project: sensors
ms.assetid: F7107D84-1963-4107-90B9-3BB4A0238530
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EVT_SENSOR_DRIVER_START_SENSOR, EVT_SENSOR_DRIVER_START_SENSOR callback, EvtSensorStart, EvtSensorStart callback function [Sensor Devices], sensors.evtsensorstart, sensorscx/EvtSensorStart
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
-	EvtSensorStart
product: Windows
targetos: Windows
req.typenames: 
---

# EVT_SENSOR_DRIVER_START_SENSOR callback function


## -description


This callback function starts the sensor based on the default properties specified by the driver, or properties set by the class extension.


## -parameters




### -param Sensor

A reference to a sensor object.


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -remarks



This function must be implemented by the driver and is called only once by the class extension.



