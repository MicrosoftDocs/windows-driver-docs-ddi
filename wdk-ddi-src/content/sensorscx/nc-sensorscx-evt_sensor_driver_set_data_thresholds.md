---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS
title: EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS (sensorscx.h)
description: This callback function sets the threshold for one or more data fields associated with a sensor.
old-location: sensors\evtsensorsetdatathresholds.htm
tech.root: sensors
ms.assetid: 297C0F35-8A18-47CF-8040-BA429963AC5F
ms.date: 05/03/2018
keywords: ["EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS callback function"]
ms.keywords: EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS, EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS callback, EvtSensorSetDataThresholds, EvtSensorSetDataThresholds callback function [Sensor Devices], sensors.evtsensorsetdatathresholds, sensorscx/EvtSensorSetDataThresholds
f1_keywords:
 - "sensorscx/EvtSensorSetDataThresholds"
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
- EvtSensorSetDataThresholds
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS callback function


## -description


This callback function sets the threshold for one or more data fields associated with a sensor.


## -parameters




### -param Sensor 

[in] A reference to a sensor object.


### -param pThresholds 

[in] A list of thresholds and their values that are set for the <b>Sensor</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a>.


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to 
		  determine if the call to the driver’s Evt function was successful, 
		  but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -remarks



This function must be implemented by the driver and is called by the class extension.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a>
 

 

