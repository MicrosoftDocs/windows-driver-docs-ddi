---
UID: NF:sensorscx.SensorsCxStateChange
title: SensorsCxStateChange function
author: windows-driver-content
description: Used to initialize a state change.
old-location: sensors\sensorscxstatechange.htm
old-project: sensors
ms.assetid: E6897994-51C7-4278-9CCE-9B7E9DD408D7
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: SensorsCxStateChange function [Sensor Devices], sensors.sensorscxstatechange, sensorscx/SensorsCxStateChange, SensorsCxStateChange
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	SensorsCx.h
apiname:
-	SensorsCxStateChange
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# SensorsCxStateChange function


## -description


Used to initialize a state change.


## -syntax


````
FORCEINLINE VOID SensorsCxStateChange(
  _In_ SENSOROBJECT Sensor,
  _In_ SENSOR_STATE State
);
````


## -parameters




### -param Sensor [in]

Holds information on the sensor being managed by the driver.


### -param State [in]

Holds information on the state of the sensor.


## -returns



This function does not return a value.



