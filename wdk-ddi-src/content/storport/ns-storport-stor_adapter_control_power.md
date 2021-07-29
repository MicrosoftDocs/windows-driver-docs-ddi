---
UID: NS:storport._STOR_ADAPTER_CONTROL_POWER
tech.root: storage
title: STOR_ADAPTER_CONTROL_POWER
ms.date: 05/13/2021
targetos: Windows
description: STOR_ADAPTER_CONTROL_POWER is the structure pointed to by the Parameters parameter when a miniport's HwStorAdapterControl routine is called with a ControlType of ScsiAdapterPower.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt:  Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: STOR_ADAPTER_CONTROL_POWER, *PSTOR_ADAPTER_CONTROL_POWER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_ADAPTER_CONTROL_POWER
 - PSTOR_ADAPTER_CONTROL_POWER
 - STOR_ADAPTER_CONTROL_POWER
f1_keywords:
 - _STOR_ADAPTER_CONTROL_POWER
 - storport/_STOR_ADAPTER_CONTROL_POWER
 - PSTOR_ADAPTER_CONTROL_POWER
 - storport/PSTOR_ADAPTER_CONTROL_POWER
 - STOR_ADAPTER_CONTROL_POWER
 - storport/STOR_ADAPTER_CONTROL_POWER
dev_langs:
 - c++
---

## -description

**STOR_ADAPTER_CONTROL_POWER** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterPower**.

## -struct-fields

### -field Header

The [**STOR_POWER_CONTROL_HEADER**](ns-storport-stor_power_control_header.md) structure.

### -field PowerAction

A [**STOR_POWER_ACTION**](ne-storport-stor_power_action.md) value that indicates the power action. For a runtime power transition, set **PowerAction** to **StorPowerActionNone**.

### -field PowerState

A [**STOR_DEVICE_POWER_STATE**](ne-storport-_stor_device_power_state.md) value that indicates the current power state. This is either **StorPowerDeviceD0** or **StorPowerDeviceD3** for the power on or power off states respectively.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)
