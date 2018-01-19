---
UID: NF:sensorscx.SensorsCxDeviceGetSensorList
title: SensorsCxDeviceGetSensorList function
author: windows-driver-content
description: This function returns a list of sensor instances associated with a WDFDEVICE.
old-location: sensors\sensorscxdevicegetsensorlist.htm
old-project: sensors
ms.assetid: C1CA7DE4-A54A-478F-9F83-585B528EF345
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SensorsCxDeviceGetSensorList
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
req.alt-api: Syntax
req.alt-loc: SensorsCx.h
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
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# SensorsCxDeviceGetSensorList function



## -description
This function returns a list of sensor instances associated with a WDFDEVICE.



## -syntax

````
FORCEINLINE NTSTATUS Syntax(
  _In_    WDFDEVICE                          FxDevice,
  _Out_   _writes_(*pListCount) SENSOROBJECT *pSensorList,
  _Inout_ PULONG                             pListCount
);
````


## -parameters

### -param FxDevice [in]

A WDFDEVICE handle to the framework device object that represents the sensor.


### -param pSensorList [out]

A list of sensor instances.


### -param pListCount [in, out]

The number of SENSOROBJECTS in pSensorInstanceList.


## -returns
This function returns NTSTATUS with different values. Some values that may be returned are the following:

STATUS_SUCCESS is returned if the function completes successfully.

STATUS_INVALID_PARAMETER is returned if any of the _In_ parameters are NULL.

STATUS_NOT_FOUND is returned if the controller is not available from the <b>FxDevice</b>.


## -remarks
