---
UID: NS:storport._STOR_POFX_POWER_CONTROL
tech.root: storage
title: STOR_POFX_POWER_CONTROL
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_POFX_POWER_CONTROL is the structure pointed to by the Parameters parameter when a miniport's HwStorUnitControl routine is called with a ControlType of ScsiUnitPoFxPowerControl or HwStorAdapterControl routine is called with a ControlType of ScsiAdapterPoFxPowerControl.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: STOR_POFX_POWER_CONTROL, *PSTOR_POFX_POWER_CONTROL
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_POFX_POWER_CONTROL
 - PSTOR_POFX_POWER_CONTROL
 - STOR_POFX_POWER_CONTROL
f1_keywords:
 - _STOR_POFX_POWER_CONTROL
 - storport/_STOR_POFX_POWER_CONTROL
 - PSTOR_POFX_POWER_CONTROL
 - storport/PSTOR_POFX_POWER_CONTROL
 - STOR_POFX_POWER_CONTROL
 - storport/STOR_POFX_POWER_CONTROL
dev_langs:
 - c++
---

## -description

**STOR_POFX_POWER_CONTROL** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine is called with a **ControlType** of **ScsiUnitPoFxPowerControl** or [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterPoFxPowerControl**.

## -struct-fields

### -field Header

The [**STOR_POWER_CONTROL_HEADER**](ns-storport-stor_power_control_header.md) structure.

### -field PowerControlCode

A power control code GUID identifying the private control operation to execute for the unit or adapter.

### -field InBufferSize

The size, in bytes, of the input buffer at **InBuffer**.

### -field OutBufferSize

The size, in bytes, of the output buffer at **OutBuffer**.

### -field InBuffer

Pointer to the buffer containing input parameters and data for the private power control call.

### -field OutBuffer

Pointer to the buffer where the resulting output parameters and data are returned for the private power control call.

### -field BytesReturned

The size, in bytes, of the data returned in **OutBuffer**.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**STOR_POWER_CONTROL_HEADER**](ns-storport-stor_power_control_header.md)
