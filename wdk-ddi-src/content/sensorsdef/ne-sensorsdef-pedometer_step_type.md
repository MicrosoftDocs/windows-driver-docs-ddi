---
UID: NE:sensorsdef.PEDOMETER_STEP_TYPE
title: PEDOMETER_STEP_TYPE
author: windows-driver-content
description: This enumeration represents the step types reported by the pedometer.
old-location: sensors\pedometer_step_type.htm
old-project: sensors
ms.assetid: 13ECDA33-2047-4F72-A8D4-5281C4BA8543
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PEDOMETER_STEP_TYPE, PEDOMETER_STEP_TYPE enumeration [Sensor Devices], PedometerStepType_Force_Dword, PedometerStepType_Max, PedometerStepType_Running, PedometerStepType_Unknown, PedometerStepType_Walking, sensors.pedometer_step_type, sensorsdef/PEDOMETER_STEP_TYPE, sensorsdef/PedometerStepType_Force_Dword, sensorsdef/PedometerStepType_Max, sensorsdef/PedometerStepType_Running, sensorsdef/PedometerStepType_Unknown, sensorsdef/PedometerStepType_Walking
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
-	PEDOMETER_STEP_TYPE
product:
- Windows
targetos: Windows
req.typenames: PEDOMETER_STEP_TYPE
req.product: Windows 10 or later.
---

# PEDOMETER_STEP_TYPE enumeration


## -description


This enumeration represents the step types reported by the pedometer.


## -enum-fields




### -field PedometerStepType_Unknown

The pedometer cannot determine the step type.


### -field PedometerStepType_Walking

Indicates a step type associated with walking.


### -field PedometerStepType_Running

Indicates a step type associated with running.


### -field PedometerStepType_Max

Indicates that the step type is generating maximum sensor values. In this scenario, the pedometer doesn't report the step type.


### -field PedometerStepType_Force_Dword

Used to force the PEDOMETER_STEP_TYPE enum to a 32-bit data type (a DWORD).


## -remarks



For more information about the sensor data fields that use this enumeration, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn957076">Pedometer data fields</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt138359">PEDOMETER_STEP_TYPE_COUNT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn957076">Pedometer data fields</a>
 

 

