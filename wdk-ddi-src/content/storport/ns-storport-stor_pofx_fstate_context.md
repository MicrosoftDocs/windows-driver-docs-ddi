---
UID: NS:storport._STOR_POFX_FSTATE_CONTEXT
tech.root: storage
title: STOR_POFX_FSTATE_CONTEXT
ms.date: 05/13/2021
targetos: Windows
description: STOR_POFX_FSTATE_CONTEXT is the structure pointed to by the Parameters parameter when a miniport's HwStorUnitControl routine is called with a ControlType of ScsiUnitPoFxPowerSetFState or HwStorAdapterControl routine is called with a ControlType of ScsiAdapterPoFxPowerSetFState.
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
req.typenames: STOR_POFX_FSTATE_CONTEXT, *PSTOR_POFX_FSTATE_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_POFX_FSTATE_CONTEXT
 - PSTOR_POFX_FSTATE_CONTEXT
 - STOR_POFX_FSTATE_CONTEXT
f1_keywords:
 - _STOR_POFX_FSTATE_CONTEXT
 - storport/_STOR_POFX_FSTATE_CONTEXT
 - PSTOR_POFX_FSTATE_CONTEXT
 - storport/PSTOR_POFX_FSTATE_CONTEXT
 - STOR_POFX_FSTATE_CONTEXT
 - storport/STOR_POFX_FSTATE_CONTEXT
dev_langs:
 - c++
---

## -description

**STOR_POFX_FSTATE_CONTEXT** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine is called with a **ControlType** of **ScsiUnitPoFxPowerSetFState** or [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterPoFxPowerSetFState**.

## -struct-fields

### -field Header

The [**STOR_POWER_CONTROL_HEADER**](ns-storport-stor_power_control_header.md) structure.

### -field ComponentIndex

Index of the device component with the active status. The component index is always 0 for both a unit device and an adapter.

### -field FState

The F-state to set for the unit or adapter component. For an adapter, the F0 state is the only component power state set.

## -remarks

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**STOR_POWER_CONTROL_HEADER**](ns-storport-stor_power_control_header.md)
