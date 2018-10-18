---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS
title: EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS
author: windows-driver-content
description: This callback function returns the thresholds that are associated with a sensor.
old-location: sensors\evtsensorgetdatathresholds.htm
tech.root: sensors
ms.assetid: 8D496490-2BB8-49A4-B575-101E61599A65
ms.date: 5/3/2018
ms.keywords: EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS, EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS callback, EvtSensorGetDataThresholds, EvtSensorGetDataThresholds callback function [Sensor Devices], sensors.evtsensorgetdatathresholds, sensorscx/EvtSensorGetDataThresholds
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
-	EvtSensorGetDataThresholds
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS callback function


## -description


This callback function returns the thresholds that are associated with a sensor.


## -parameters




### -param Sensor

[in] A reference to a sensor object.


### -param pThresholds

[out] A list of threshold properties and their values associated with the <b>Sensor</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn957092">SENSOR_COLLECTION_LIST</a>.


### -param pSize


The size of *pThresholds*.





## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to 
		  determine if the call to the driver’s Evt function was successful, 
		  but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -remarks



This function must be implemented by the driver and is called by the class extension.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn957092">SENSOR_COLLECTION_LIST</a>
 

 

