---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_PROPERTIES
title: EVT_SENSOR_DRIVER_GET_PROPERTIES
author: windows-driver-content
description: This callback function returns the properties for a given sensor.
old-location: sensors\evtsensorgetproperties.htm
old-project: sensors
ms.assetid: 259C37C9-DE8C-4BC8-B18A-CDD96B97056D
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: EVT_SENSOR_DRIVER_GET_PROPERTIES, EVT_SENSOR_DRIVER_GET_PROPERTIES callback, EvtSensorGetProperties, EvtSensorGetProperties callback function [Sensor Devices], sensors.evtsensorgetproperties, sensorscx/EvtSensorGetProperties
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
-	EvtSensorGetProperties
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SENSOR_DRIVER_GET_PROPERTIES callback function


## -description


This callback function returns the properties for a given sensor.


## -parameters




### -param Sensor [in]

A reference to a sensor object.


### -param pProperties [in, out, optional]

A list of properties and their values for the specified <b>Sensor</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn957092">SENSOR_COLLECTION_LIST</a>.


### -param pSize [out]

The size of pProperties.


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -remarks



This function must be implemented by the driver and is called by the class extension.



