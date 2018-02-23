---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION
title: EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION
author: windows-driver-content
description: Used to start a state change notification.
old-location: sensors\evt_sensor_driver_start_state_change_notification.htm
old-project: sensors
ms.assetid: 93C2ABCE-15C9-4EE4-A9B5-A81788DB608C
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: sensors.evt_sensor_driver_start_state_change_notification, EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION callback function [Sensor Devices], EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION, EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION, EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION, sensorscx/EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION
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
-	EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION callback


## -description


Used to start a state change notification.


## -prototype


````
NTSTATUS  EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION(
  _In_ SENSOROBJECT Sensors
);
````


## -parameters




### -param Sensors [in]

Holds information on the sensors handled by the sensor driver.


## -returns



Returns STATUS_SUCCESS if completed successfully.



