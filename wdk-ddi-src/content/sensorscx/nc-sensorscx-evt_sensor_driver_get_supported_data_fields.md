---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS
title: EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS
description: This callback function returns a list of data fields supported by the specified sensor.
old-location: sensors\evtsensorgetsupporteddatafields.htm
tech.root: sensors
ms.assetid: 8C73DFE2-E87A-460D-8EBE-CF3767CAA23F
ms.date: 05/03/2018
ms.keywords: EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS, EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS callback, EvtSensorGetSupportedDataFields, EvtSensorGetSupportedDataFields callback function [Sensor Devices], sensors.evtsensorgetsupporteddatafields, sensorscx/EvtSensorGetSupportedDataFields
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
-	EvtSensorGetSupportedDataFields
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS callback function


## -description


This callback function returns a list of data fields supported by the specified sensor.

For more information about data fields, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn946691">Sensor data fields</a>.


## -parameters




### -param Sensor

[in] A reference to a sensor object.


### -param pDataFields

[in, out, optional] A list of data fields that are supported by the given <b>Sensor</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn946699">SENSOR_PROPERTY_LIST</a>.


### -param pSize 

[out] The size of *pDataFields*.


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -remarks



This function must be implemented by the driver and is called by the class extension.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn946699">SENSOR_PROPERTY_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn946691">Sensor data fields</a>
 

 

