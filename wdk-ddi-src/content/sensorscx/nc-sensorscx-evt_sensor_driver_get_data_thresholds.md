---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS
title: EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS
author: windows-driver-content
description: This callback function returns the thresholds that are associated with a sensor.
old-location: sensors\evtsensorgetdatathresholds.htm
old-project: sensors
ms.assetid: 8D496490-2BB8-49A4-B575-101E61599A65
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS, EvtSensorGetDataThresholds, EvtSensorGetDataThresholds callback function [Sensor Devices], sensors.evtsensorgetdatathresholds, sensorscx/EvtSensorGetDataThresholds
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
-	EvtSensorGetDataThresholds
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS callback


## -description


This callback function returns the thresholds that are associated with a sensor.


## -prototype


````
NTSTATUS EvtSensorGetDataThresholds(
  _In_  SENSOROBJECT            Sensor,
  _Out_ PSENSOR_COLLECTION_LIST pThresholds
);
````


## -parameters




### -param Sensor [in]

A reference to a sensor object.


### -param pThresholds [out]

A list of threshold properties and their values associated with the <b>Sensor</b>. For more information, see <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>.


### -param pSize








## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to 
		  determine if the call to the driver’s Evt function was successful, 
		  but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -remarks



This function must be implemented by the driver and is called by the class extension.




## -see-also

<a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

