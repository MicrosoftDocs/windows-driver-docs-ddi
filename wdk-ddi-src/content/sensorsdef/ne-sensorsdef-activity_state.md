---
UID: NE:sensorsdef.ACTIVITY_STATE
title: ACTIVITY_STATE
author: windows-driver-content
description: This enumeration represents the activity states reported by the activity detection sensor.
old-location: sensors\activity_states.htm
old-project: sensors
ms.assetid: E602F16A-AFD8-4698-AC90-1686887FFEA6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ACTIVITY_STATE, ACTIVITY_STATE enumeration [Sensor Devices], ActivityState_Biking, ActivityState_Fidgeting, ActivityState_Force_Dword, ActivityState_Idle, ActivityState_InVehicle, ActivityState_Max, ActivityState_Running, ActivityState_Stationary, ActivityState_Unknown, ActivityState_Walking, sensors.activity_states, sensorsdef/ACTIVITY_STATE, sensorsdef/ActivityState_Biking, sensorsdef/ActivityState_Fidgeting, sensorsdef/ActivityState_Force_Dword, sensorsdef/ActivityState_Idle, sensorsdef/ActivityState_InVehicle, sensorsdef/ActivityState_Max, sensorsdef/ActivityState_Running, sensorsdef/ActivityState_Stationary, sensorsdef/ActivityState_Unknown, sensorsdef/ActivityState_Walking
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sensorsdef.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Sensorsdef.h
api_name:
-	ACTIVITY_STATE
product: Windows
targetos: Windows
req.typenames: ACTIVITY_STATE
req.product: Windows 10 or later.
---

# ACTIVITY_STATE enumeration


## -description


This enumeration represents the activity states reported by the activity detection sensor.


## -enum-fields




### -field ActivityState_Unknown

The sensor cannot accurately determine the current activity.


### -field ActivityState_Stationary

Indicates that the sensor is currently stationary.


### -field ActivityState_Fidgeting

Describes the current activity as "fidgeting."


### -field ActivityState_Walking

Describes the current activity as "walking."


### -field ActivityState_Running

Describes the current activity as "running."


### -field ActivityState_InVehicle

Describes the current activity as "traveling in a vehicle."


### -field ActivityState_Biking

Describes the current activity as "biking."


### -field ActivityState_Idle

Describes the current activity as "idle."


### -field ActivityState_Max

Indicates that the current activity state is generating maximum sensor values. In this scenario the sensor doesn't indicate what the activity is.


### -field ActivityState_Force_Dword

Used to force the ACTIVITY_STATE enum to a 32-bit data type (a DWORD).


## -remarks



For more information about the sensor data fields that use this enumeration, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn957013">Activity detection sensor data fields</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn957013">Activity detection sensor data fields</a>
 

 

