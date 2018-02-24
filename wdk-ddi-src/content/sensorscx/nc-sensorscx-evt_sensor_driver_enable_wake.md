---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_ENABLE_WAKE
title: EVT_SENSOR_DRIVER_ENABLE_WAKE
author: windows-driver-content
description: Callback to enable wake for the sensor.
old-location: sensors\evt_sensor_driver_enable_wake.htm
old-project: sensors
ms.assetid: 969E08D1-0D4A-4FED-9722-4EDA067C522C
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: sensors.evt_sensor_driver_enable_wake, EVT_SENSOR_DRIVER_ENABLE_WAKE callback function [Sensor Devices], EVT_SENSOR_DRIVER_ENABLE_WAKE, sensorscx/EVT_SENSOR_DRIVER_ENABLE_WAKE
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
-	EVT_SENSOR_DRIVER_ENABLE_WAKE
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_ENABLE_WAKE callback


## -description


Callback to enable wake for the sensor. 


## -prototype


````
NTSTATUS CALLBACK EVT_SENSOR_DRIVER_ENABLE_WAKE(
  _In_ SENSOROBJECT Sensor
);
````


## -parameters




### -param Sensor [in]

A reference to the sensor object


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<div class="alert"><b>Note</b>  The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.</div>
<div> </div>



## -remarks



This DDSI function does not compulsorily have to be implemented by the driver because it is expected that some sensor drivers do not care about enabling wake on the sensor. If it not implemented the enable call is ignored and a STATUS_SUCCESS is returned. This is primarily because PKEY_Sensor_WakeCapable is implemented today and used by some sensors such as the accelerometer and the proximity sensor, and for backward compatibility, implementing this DDSI is optional.



