---
UID: NE:wdm._PO_EFFECTIVE_POWER_MODE
tech.root: kernel
title: PO_EFFECTIVE_POWER_MODE (wdm.h)
ms.date: 03/04/2024
targetos: Windows
description: The PO_EFFECTIVE_POWER_MODE enumeration constants indicates the effective power mode the system is running.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PO_EFFECTIVE_POWER_MODE
 - PPO_EFFECTIVE_POWER_MODE
 - PO_EFFECTIVE_POWER_MODE
f1_keywords:
 - _PO_EFFECTIVE_POWER_MODE
 - wdm/_PO_EFFECTIVE_POWER_MODE
 - PPO_EFFECTIVE_POWER_MODE
 - wdm/PPO_EFFECTIVE_POWER_MODE
 - PO_EFFECTIVE_POWER_MODE
 - wdm/PO_EFFECTIVE_POWER_MODE
dev_langs:
 - c++
helpviewer_keywords:
 - _PO_EFFECTIVE_POWER_MODE
---

# PO_EFFECTIVE_POWER_MODE enumeration (wdm.h)

## -description

The **PO_EFFECTIVE_POWER_MODE** enumeration constants indicates the effective power mode the system is running.

## -enum-fields

### -field PoEffectivePowerModeBatterySaver

The system is in battery saver effective power mode.

### -field PoEffectivePowerModeEnergySaverHighSavings

The system is in energy saver high savings effective power mode.

### -field PoEffectivePowerModeBetterBattery

The system is in better battery effective power mode. For systems using the legacy high performance overlay, this effective power mode will never be used.

### -field PoEffectivePowerModeEnergySaverStandard

The system is in the energy saver standard effective power mode.

### -field PoEffectivePowerModeBalanced

The system is in the balanced effective power mode.

### -field PoEffectivePowerModeHighPerformance

The system is in the high performance effective power mode. This power mode is only used for systems using the legacy high performance overlay.

### -field PoEffectivePowerModeMaxPerformance

The system is in the maximum performance effective power mode.

### -field PoEffectivePowerModeGameMode

The system is in game mode effective power mode.

### -field PoEffectivePowerModeMixedReality

The system is in the Windows Mixed Reality effective power mode.

## -remarks

## -see-also

[PO_EFFECTIVE_POWER_MODE_CALLBACK](nc-wdm-po_effective_power_mode_callback.md)

[PoRegisterForEffectivePowerModeNotifications](nf-wdm-poregisterforeffectivepowermodenotifications.md)

[PoUnregisterFromEffectivePowerModeNotifications](nf-wdm-pounregisterfromeffectivepowermodenotifications.md)
