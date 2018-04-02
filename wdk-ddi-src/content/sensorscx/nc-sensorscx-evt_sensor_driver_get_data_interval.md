---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_DATA_INTERVAL
title: EVT_SENSOR_DRIVER_GET_DATA_INTERVAL
author: windows-driver-content
description: This callback function returns the data interval for a specified sensor.
old-location: sensors\evtsensorgetdatainterval.htm
old-project: sensors
ms.assetid: 2C53ABFD-127C-42E6-86B6-EB0DC6FC62F1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EVT_SENSOR_DRIVER_GET_DATA_INTERVAL, EvtSensorGetDataInterval, EvtSensorGetDataInterval callback function [Sensor Devices], sensors.evtsensorgetdatainterval, sensorscx/EvtSensorGetDataInterval
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
-	EvtSensorGetDataInterval
product:
- Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_GET_DATA_INTERVAL callback


## -description


This callback function returns the data interval for a specified sensor.


## -parameters




### -param Sensor [in]

A reference to a sensor object.


### -param pDataRateMs [out]

The data interval for the specified <b>Sensor</b>.


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to 
		  determine if the call to the driver’s Evt function was successful, 
		  but does not take any action if the function failed or does not return STATUS_SUCCESS.



