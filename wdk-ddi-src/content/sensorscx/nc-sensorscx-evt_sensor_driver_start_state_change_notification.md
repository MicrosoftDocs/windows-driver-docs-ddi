---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION
title: EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION (sensorscx.h)
description: Used to start a state change notification.
old-location: sensors\evt_sensor_driver_start_state_change_notification.htm
tech.root: sensors
ms.assetid: 93C2ABCE-15C9-4EE4-A9B5-A81788DB608C
ms.date: 05/03/2018
keywords: ["EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION callback function"]
ms.keywords: EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION, EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION callback, EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION callback function [Sensor Devices], sensors.evt_sensor_driver_start_state_change_notification, sensorscx/EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION
f1_keywords:
 - "sensorscx/EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION"
 - "EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- sensorscx.h
api_name:
- EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION
targetos: Windows
req.typenames: 
---

# EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION callback function


## -description


Used to start a state change notification.


## -parameters




### -param Sensors

[in] Holds information on the sensors handled by the sensor driver.


## -returns



Returns STATUS_SUCCESS if completed successfully.



