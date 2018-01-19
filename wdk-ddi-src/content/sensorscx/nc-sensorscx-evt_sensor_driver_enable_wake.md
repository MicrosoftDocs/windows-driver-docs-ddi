---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_ENABLE_WAKE
title: EVT_SENSOR_DRIVER_ENABLE_WAKE
author: windows-driver-content
description: Callback to enable wake for the sensor.
old-location: sensors\evt_sensor_driver_enable_wake.htm
old-project: sensors
ms.assetid: 969E08D1-0D4A-4FED-9722-4EDA067C522C
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorDriver, ISensorDriver::OnSetProperties, OnSetProperties
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
req.alt-api: EVT_SENSOR_DRIVER_ENABLE_WAKE
req.alt-loc: SensorsCx.h
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


## -remarks
This DDSI function does not compulsorily have to be implemented by the driver because it is expected that some sensor drivers do not care about enabling wake on the sensor. If it not implemented the enable call is ignored and a STATUS_SUCCESS is returned. This is primarily because PKEY_Sensor_WakeCapable is implemented today and used by some sensors such as the accelerometer and the proximity sensor, and for backward compatibility, implementing this DDSI is optional.</p>