---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS
title: EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS
author: windows-driver-content
description: This callback function returns a list of data fields supported by the specified sensor.
old-location: sensors\evtsensorgetsupporteddatafields.htm
old-project: sensors
ms.assetid: 8C73DFE2-E87A-460D-8EBE-CF3767CAA23F
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS, EvtSensorGetSupportedDataFields, EvtSensorGetSupportedDataFields callback function [Sensor Devices], sensors.evtsensorgetsupporteddatafields, sensorscx/EvtSensorGetSupportedDataFields
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
-	EvtSensorGetSupportedDataFields
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS callback


## -description


This callback function returns a list of data fields supported by the specified sensor.

For more information about data fields, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn946691">Sensor data fields</a>.


## -prototype


````
NT_STATUS EvtSensorGetSupportedDataFields(
  _In_        SENSOROBJECT          Sensor,
  _Inout_opt_ PSENSOR_PROPERTY_LIST pDataFields,
  _Out_       PULONG                pSize
);
````


## -parameters




### -param Sensor [in]

A reference to a sensor object.


### -param pDataFields [in, out, optional]

A list of data fields that are supported by the given <b>Sensor</b>. For more information, see <a href="..\sensorsdef\ns-sensorsdef-sensor_property_list.md">SENSOR_PROPERTY_LIST</a>.


### -param pSize [out]

The size of <b>pFields</b>.


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -remarks



This function must be implemented by the driver and is called by the class extension.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946691">Sensor data fields</a>



<a href="..\sensorsdef\ns-sensorsdef-sensor_property_list.md">SENSOR_PROPERTY_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

