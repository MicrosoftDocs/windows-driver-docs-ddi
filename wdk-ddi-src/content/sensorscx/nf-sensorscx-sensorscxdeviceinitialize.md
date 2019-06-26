---
UID: NF:sensorscx.SensorsCxDeviceInitialize
title: SensorsCxDeviceInitialize function (sensorscx.h)
description: This function initializes the sensor in the class extension.
old-location: sensors\sensorscxdeviceinitialize.htm
tech.root: sensors
ms.assetid: F6F758AC-5C8C-4226-B906-972C5BCD7A3E
ms.date: 05/03/2018
ms.keywords: SensorsCxDeviceInitialize, SensorsCxDeviceInitialize function [Sensor Devices], sensors.sensorscxdeviceinitialize, sensorscx/SensorsCxDeviceInitialize
ms.topic: function
req.header: sensorscx.h
req.include-header: 
req.target-type: Desktop
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- SensorsCx.h
api_name:
- SensorsCxDeviceInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# SensorsCxDeviceInitialize function


## -description


This function initializes the sensor in the class extension.


## -parameters




### -param FxDevice [in]

A WDFDEVICE handle to the framework device object that represents the sensor.


### -param pSensorConfig [in]

A list of functions that the driver implements. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorscx/ns-sensorscx-_sensor_controller_config">SENSOR_CONTROLLER_CONFIG</a>.


## -returns



This function returns STATUS_SUCCESS when completed successfully. When an invalid parameter is supplied or this function fails, STATUS_INVALID_PARAMETER is returned. Other NTSTATUS values can also be returned.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorscx/ns-sensorscx-_sensor_controller_config">SENSOR_CONTROLLER_CONFIG</a>
 

 

