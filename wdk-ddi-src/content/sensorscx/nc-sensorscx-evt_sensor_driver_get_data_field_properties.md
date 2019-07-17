---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES
title: EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES (sensorscx.h)
description: This callback function returns the properties of a given data field associated with a sensor.
old-location: sensors\evtsensorgetdatafieldproperties.htm
tech.root: sensors
ms.assetid: E3BE0351-724E-4407-AA5B-D7AAEFE508D4
ms.date: 05/03/2018
ms.keywords: EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES, EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES callback, EvtSensorGetDataFieldProperties, EvtSensorGetDataFieldProperties callback function [Sensor Devices], sensors.evtsensorgetdatafieldproperties, sensorscx/EvtSensorGetDataFieldProperties
ms.topic: callback
f1_keywords:
 - "sensorscx/EvtSensorGetDataFieldProperties"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- SensorsCx.h
api_name:
- EvtSensorGetDataFieldProperties
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES callback function


## -description


This callback function returns the properties of a given data field associated with a sensor.


## -parameters




### -param Sensor

[in] A reference to a sensor object.


### -param pDataField

[in] A reference to a data field. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/sensors/sensor-data-fields">Sensor data fields</a>.


### -param pProperties

[in, out, optional] A list of properties and their values for the specified <b>Sensor</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a>.


### -param pSize

[out] The size of <b>pDataField</b>.


## -returns



This function returns STATUS_SUCCESS when completed successfully.




## -remarks



This function must be implemented by the driver and is called by the class extension.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/sensors/proximity-sensor-data-fields">Proximity sensor data fields</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/sensors/sensor-data-fields">Sensor data fields</a>
 

 

