---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES
title: EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES
author: windows-driver-content
description: This callback function returns the properties of a given data field associated with a sensor.
old-location: sensors\evtsensorgetdatafieldproperties.htm
old-project: sensors
ms.assetid: E3BE0351-724E-4407-AA5B-D7AAEFE508D4
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES, EvtSensorGetDataFieldProperties, EvtSensorGetDataFieldProperties callback function [Sensor Devices], sensors.evtsensorgetdatafieldproperties, sensorscx/EvtSensorGetDataFieldProperties
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
-	EvtSensorGetDataFieldProperties
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES callback


## -description


This callback function returns the properties of a given data field associated with a sensor.


## -prototype


````
NT_STATUS EvtSensorGetDataFieldProperties(
  _In_        SENSOROBJECT            Sensor,
  _In_        CONST                   *pDataField,
  _Inout_opt_ PSENSOR_COLLECTION_LIST pProperties,
  _Out_       PULONG                  pSize
);
````


## -parameters




### -param Sensor [in]

A reference to a sensor object.


### -param pDataField [in]

A reference to a data field. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn946691">Sensor data fields</a>.


### -param pProperties [in, out, optional]

A list of properties and their values for the specified <b>Sensor</b>. For more information, see <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>.


### -param pSize [out]

The size of <b>pDataField</b>.


## -returns



This function returns STATUS_SUCCESS when completed successfully.




## -remarks



This function must be implemented by the driver and is called by the class extension.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -see-also

<a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn946691">Sensor data fields</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn957080">Proximity sensor data fields</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

