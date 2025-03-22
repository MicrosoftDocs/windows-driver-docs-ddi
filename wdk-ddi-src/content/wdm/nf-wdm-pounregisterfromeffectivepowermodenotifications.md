---
UID: NF:wdm.PoUnregisterFromEffectivePowerModeNotifications
tech.root: kernel
title: PoUnregisterFromEffectivePowerModeNotifications (wdm.h)
ms.date: 03/04/2024
targetos: Windows
description: The PoUnregisterFromEffectivePowerModeNotifications function unregisters from effective power mode change notifications.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type:
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PoUnregisterFromEffectivePowerModeNotifications
f1_keywords:
 - PoUnregisterFromEffectivePowerModeNotifications
 - wdm/PoUnregisterFromEffectivePowerModeNotifications
dev_langs:
 - c++
helpviewer_keywords:
 - PoUnregisterFromEffectivePowerModeNotifications
---

# PoUnregisterFromEffectivePowerModeNotifications function (wdm.h)

## -description

The **PoUnregisterFromEffectivePowerModeNotifications** function unregisters from effective power mode change notifications. This function is intended to be called from cleanup code and will wait for all callbacks to complete before unregistering.

## -parameters

### -param RegistrationHandle

The handle corresponding to a single power mode registration. This handle should have been saved by the caller after the call to PowerRegisterForEffectivePowerModeNotifications and passed in here.

## -returns

Returns S_OK (zero) if the call was successful, and a nonzero value if the call failed.

## -remarks

Immediately after registration, the callback will be invoked with the current value of the power setting. If the registration occurs while the power setting is changing, you may receive multiple callbacks; the last callback is the most recent update.

## -see-also

[**PO_EFFECTIVE_POWER_MODE**](ne-wdm-po_effective_power_mode.md)

[PO_EFFECTIVE_POWER_MODE_CALLBACK](nc-wdm-po_effective_power_mode_callback.md)

[PoRegisterForEffectivePowerModeNotifications](nf-wdm-poregisterforeffectivepowermodenotifications.md)
