---
UID: NS:storport._STOR_POFX_UNIT_POWER_INFO
tech.root: storage
title: STOR_POFX_UNIT_POWER_INFO
ms.date: 5/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_POFX_UNIT_POWER_INFO is the structure pointed to by the Parameters parameter when a miniport's HwStorUnitControl routine is called with a ControlType of ScsiUnitPoFxPowerInfo.
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
req.typenames: STOR_POFX_UNIT_POWER_INFO, *PSTOR_POFX_UNIT_POWER_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_POFX_UNIT_POWER_INFO
 - PSTOR_POFX_UNIT_POWER_INFO
 - STOR_POFX_UNIT_POWER_INFO
f1_keywords:
 - _STOR_POFX_UNIT_POWER_INFO
 - storport/_STOR_POFX_UNIT_POWER_INFO
 - PSTOR_POFX_UNIT_POWER_INFO
 - storport/PSTOR_POFX_UNIT_POWER_INFO
 - STOR_POFX_UNIT_POWER_INFO
 - storport/STOR_POFX_UNIT_POWER_INFO
dev_langs:
 - c++
---

## -description

**STOR_POFX_UNIT_POWER_INFO** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine is called with a **ControlType** of **ScsiUnitPoFxPowerInfo**.

## -struct-fields

### -field Header

The [**STOR_POWER_CONTROL_HEADER**](ns-storport-stor_power_control_header.md) structure.

### -field IdlePowerEnabled

**TRUE** if idle power management is enabled for the unit. Otherwise, **FALSE**.

## -see-also

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**STOR_POWER_CONTROL_HEADER**](ns-storport-stor_power_control_header.md)
