---
UID: NE:sensorsdef.PEDOMETER_STEP_TYPE
title: PEDOMETER_STEP_TYPE (sensorsdef.h)
description: This enumeration represents the step types reported by the pedometer.
old-location: sensors\pedometer_step_type.htm
tech.root: sensors
ms.assetid: 13ECDA33-2047-4F72-A8D4-5281C4BA8543
ms.date: 05/03/2018
keywords: ["PEDOMETER_STEP_TYPE enumeration"]
ms.keywords: PEDOMETER_STEP_TYPE, PEDOMETER_STEP_TYPE enumeration [Sensor Devices], PedometerStepType_Force_Dword, PedometerStepType_Max, PedometerStepType_Running, PedometerStepType_Unknown, PedometerStepType_Walking, sensors.pedometer_step_type, sensorsdef/PEDOMETER_STEP_TYPE, sensorsdef/PedometerStepType_Force_Dword, sensorsdef/PedometerStepType_Max, sensorsdef/PedometerStepType_Running, sensorsdef/PedometerStepType_Unknown, sensorsdef/PedometerStepType_Walking
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
targetos: Windows
req.typenames: PEDOMETER_STEP_TYPE
f1_keywords:
 - PEDOMETER_STEP_TYPE
 - sensorsdef/PEDOMETER_STEP_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Sensorsdef.h
api_name:
 - PEDOMETER_STEP_TYPE
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

For more information about the sensor data fields that use this enumeration, see <a href="/windows-hardware/drivers/sensors/pedometer-data-fields">Pedometer data fields</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sensorsdef/ne-sensorsdef-pedometer_step_type_count">PEDOMETER_STEP_TYPE_COUNT</a>



<a href="/windows-hardware/drivers/sensors/pedometer-data-fields">Pedometer data fields</a>