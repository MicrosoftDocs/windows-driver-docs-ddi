---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
title: EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
author: windows-driver-content
description: Used to stop a state change notification.
old-location: sensors\evt_sensor_driver_stop_state_change_notification.htm
old-project: sensors
ms.assetid: 53B064AF-D06B-46A0-9D77-2DA72F0B47D6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: sensors.evt_sensor_driver_stop_state_change_notification, EvtSensorDriverStopStateChangeNotification callback function [Sensor Devices], EvtSensorDriverStopStateChangeNotification, EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION, EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION, sensorscx/EvtSensorDriverStopStateChangeNotification, PFN_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION callback function pointer [Sensor Devices], PFN_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
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
-	sensorscx.h
apiname:
-	PFN_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION callback


## -description


Used to stop a state change notification.


## -prototype


````
NTSTATUS EvtSensorDriverStopStateChangeNotification(
   SENSOROBJECT Sensors
);
````


## -parameters




### -param Sensors

Holds information on the sensor being handled by the driver.


## -returns



Returns STATUS_SUCCESS if completed successfully.



