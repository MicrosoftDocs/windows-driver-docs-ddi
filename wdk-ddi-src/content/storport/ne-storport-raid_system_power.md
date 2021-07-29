---
UID: NE:storport._RAID_SYSTEM_POWER
tech.root: storage
title: RAID_SYSTEM_POWER
ms.date: 05/13/2021
targetos: Windows
description: RAID_SYSTEM_POWER is a system power usage indicator.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _RAID_SYSTEM_POWER
 - PRAID_SYSTEM_POWER
 - RAID_SYSTEM_POWER
f1_keywords:
 - _RAID_SYSTEM_POWER
 - storport/_RAID_SYSTEM_POWER
 - PRAID_SYSTEM_POWER
 - storport/PRAID_SYSTEM_POWER
 - RAID_SYSTEM_POWER
 - storport/RAID_SYSTEM_POWER
dev_langs:
 - c++
---

## -description

**RAID_SYSTEM_POWER** is a system power usage indicator.

## -enum-fields

### -field RaidSystemPowerUnknown

The power usage is unknown.

### -field RaidSystemPowerLowest

Lowest power usage.

### -field RaidSystemPowerLow

Low power usage.

### -field RaidSystemPowerMedium

Medium power usage.

### -field RaidSystemPowerHigh

High power usage.

## -remarks

**RAID_SYSTEM_POWER** is a member of the [**STOR_SYSTEM_POWER_HINTS**](ns-storport-stor_system_power_hints.md) structure.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**STOR_SYSTEM_POWER_HINTS**](ns-storport-stor_system_power_hints.md)
