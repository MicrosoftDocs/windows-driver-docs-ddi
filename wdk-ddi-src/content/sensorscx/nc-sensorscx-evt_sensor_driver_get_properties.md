---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_PROPERTIES
title: EVT_SENSOR_DRIVER_GET_PROPERTIES (sensorscx.h)
description: This callback function returns the properties for a given sensor.
old-location: sensors\evtsensorgetproperties.htm
tech.root: sensors
ms.assetid: 259C37C9-DE8C-4BC8-B18A-CDD96B97056D
ms.date: 05/03/2018
keywords: ["EVT_SENSOR_DRIVER_GET_PROPERTIES callback function"]
ms.keywords: EVT_SENSOR_DRIVER_GET_PROPERTIES, EVT_SENSOR_DRIVER_GET_PROPERTIES callback, EvtSensorGetProperties, EvtSensorGetProperties callback function [Sensor Devices], sensors.evtsensorgetproperties, sensorscx/EvtSensorGetProperties
f1_keywords:
 - "sensorscx/EvtSensorGetProperties"
 - "EvtSensorGetProperties"
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
- SensorsCx.h
api_name:
- EvtSensorGetProperties
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SENSOR_DRIVER_GET_PROPERTIES callback function


## -description


This callback function returns the properties for a given sensor.


## -parameters




### -param Sensor

[in] A reference to a sensor object.


### -param pProperties

[in, out, optional] A list of properties and their values for the specified <b>Sensor</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a>.


### -param pSize

[out] The size of pProperties.


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -remarks



This function must be implemented by the driver and is called by the class extension.



