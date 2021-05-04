---
UID: NS:storport._STOR_POFX_POWER_REQUIRED_CONTEXT
tech.root: storage
title: STOR_POFX_POWER_REQUIRED_CONTEXT
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_POFX_POWER_REQUIRED_CONTEXT is the structure pointed to by the Parameters parameter when a miniport's HwStorUnitControl routine is called with a ControlType of ScsiUnitPoFxPowerRequired.
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
req.typenames: STOR_POFX_POWER_REQUIRED_CONTEXT, *PSTOR_POFX_POWER_REQUIRED_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_POFX_POWER_REQUIRED_CONTEXT
 - PSTOR_POFX_POWER_REQUIRED_CONTEXT
 - STOR_POFX_POWER_REQUIRED_CONTEXT
f1_keywords:
 - _STOR_POFX_POWER_REQUIRED_CONTEXT
 - storport/_STOR_POFX_POWER_REQUIRED_CONTEXT
 - PSTOR_POFX_POWER_REQUIRED_CONTEXT
 - storport/PSTOR_POFX_POWER_REQUIRED_CONTEXT
 - STOR_POFX_POWER_REQUIRED_CONTEXT
 - storport/STOR_POFX_POWER_REQUIRED_CONTEXT
dev_langs:
 - c++
---

## -description

**STOR_POFX_POWER_REQUIRED_CONTEXT** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine is called with a **ControlType** of **ScsiUnitPoFxPowerRequired**.

## -struct-fields

### -field Header

The [**STOR_POWER_CONTROL_HEADER**](ns-storport-stor_power_control_header.md) structure.

### -field PowerRequired

**TRUE** if the unit component requires power. Otherwise, **FALSE.**

## -see-also

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**STOR_POWER_CONTROL_HEADER**](ns-storport-stor_power_control_header.md)
