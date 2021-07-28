---
UID: NS:storport._STOR_SYSTEM_POWER_HINTS
tech.root: storage
title: STOR_SYSTEM_POWER_HINTS
ms.date: 05/13/2021
targetos: Windows
description: STOR_SYSTEM_POWER_HINTS is the structure pointed to by the Parameters parameter when a miniport's HwStorAdapterControl routine is called with a ControlType of ScsiAdapterSystemPowerHints.
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
req.typenames: STOR_SYSTEM_POWER_HINTS, *PSTOR_SYSTEM_POWER_HINTS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_SYSTEM_POWER_HINTS
 - PSTOR_SYSTEM_POWER_HINTS
 - STOR_SYSTEM_POWER_HINTS
f1_keywords:
 - _STOR_SYSTEM_POWER_HINTS
 - storport/_STOR_SYSTEM_POWER_HINTS
 - PSTOR_SYSTEM_POWER_HINTS
 - storport/PSTOR_SYSTEM_POWER_HINTS
 - STOR_SYSTEM_POWER_HINTS
 - storport/STOR_SYSTEM_POWER_HINTS
dev_langs:
 - c++
---

## -description

**STOR_SYSTEM_POWER_HINTS** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterSystemPowerHints**.

## -struct-fields

### -field Version

Version number of this structure. Currently set to STOR_SYSTEM_POWER_HINTS_V1.

### -field Size

Size of this structure, in bytes. Set to ```sizeof(STOR_SYSTEM_POWER_HINTS)```.

### -field SystemPower

A [**RAID_SYSTEM_POWER**](ne-storport-raid_system_power.md) enum value that indicates the system's current power usage.

### -field ResumeLatencyMSec

The maximum resume latency tolerated for the given system power hint, in milliseconds.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**RAID_SYSTEM_POWER**](ne-storport-raid_system_power.md)
