---
UID: NF:sensorscx.SensorsCxDeviceGetSensorList
title: SensorsCxDeviceGetSensorList function
author: windows-driver-content
description: This function returns a list of sensor instances associated with a WDFDEVICE.
old-location: sensors\sensorscxdevicegetsensorlist.htm
old-project: sensors
ms.assetid: C1CA7DE4-A54A-478F-9F83-585B528EF345
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: SensorsCxDeviceGetSensorList, Syntax, Syntax function [Sensor Devices], sensors.sensorscxdevicegetsensorlist, sensorscx/Syntax
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	SensorsCx.h
api_name:
-	Syntax
product:
- Windows
targetos: Windows
req.typenames: 
---

# SensorsCxDeviceGetSensorList function


## -description


This function returns a list of sensor instances associated with a WDFDEVICE.


## -parameters




### -param FxDevice [in]

A WDFDEVICE handle to the framework device object that represents the sensor.


### -param pSensorList [out]

A list of sensor instances.


### -param pListCount [in, out]

The number of SENSOROBJECTS in pSensorInstanceList.


## -returns



This function returns NTSTATUS with different values. Some values that may be returned are the following:

<ul>
<li>
STATUS_SUCCESS is returned if the function completes successfully.

</li>
<li>
STATUS_INVALID_PARAMETER is returned if any of the _In_ parameters are NULL.

</li>
<li>
STATUS_NOT_FOUND is returned if the controller is not available from the <b>FxDevice</b>.

</li>
</ul>


