---
UID: NE:sensorsdef.SENSOR_STATE
title: SENSOR_STATE
author: windows-driver-content
description: This enumeration represents the valid states of a sensor.
old-location: sensors\sensor_state.htm
old-project: sensors
ms.assetid: F1E869AE-2FAF-402F-9C50-58D81E0EFF69
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: SensorState_Initializing, SENSOR_STATE, sensorsdef/SENSOR_STATE, SensorState_Idle, SensorState_Error, sensorsdef/SensorState_Active, sensorsdef/SensorState_Initializing, SENSOR_STATE enumeration [Sensor Devices], sensorsdef/SensorState_Idle, SensorState_Active, sensorsdef/SensorState_Error, sensors.sensor_state
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sensorsdef.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Sensorsdef.h
apiname:
-	SENSOR_STATE
product: Windows
targetos: Windows
req.typenames: SENSOR_STATE
req.product: Windows 10 or later.
---

# SENSOR_STATE enumeration


## -description


This enumeration represents the valid states of a sensor.


## -syntax


````
typedef enum _SENSOR_STATE { 
  SensorState_Initializing  = 0,
  SensorState_Idle,
  SensorState_Active,
  SensorState_Error
} SENSOR_STATE;
````


## -enum-fields




### -field SensorState_Initializing

Indicates that the sensor is initializing.


### -field SensorState_Idle

Indicates that the sensor is idle


### -field SensorState_Active

Indicates that the sensor is active.


### -field SensorState_Error

Indicates that the sensor is in an error state.

