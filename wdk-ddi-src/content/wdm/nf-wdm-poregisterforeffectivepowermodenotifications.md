---
UID: NF:wdm.PoRegisterForEffectivePowerModeNotifications
tech.root: kernel
title: PoRegisterForEffectivePowerModeNotifications (wdm.h)
ms.date: 03/04/2024
targetos: Windows
description: The PoRegisterForEffectivePowerModeNotifications function registers a callback to receive effective power mode change notifications.
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
 - PoRegisterForEffectivePowerModeNotifications
f1_keywords:
 - PoRegisterForEffectivePowerModeNotifications
 - wdm/PoRegisterForEffectivePowerModeNotifications
dev_langs:
 - c++
helpviewer_keywords:
 - PoRegisterForEffectivePowerModeNotifications
---

# PoRegisterForEffectivePowerModeNotifications function (wdm.h)

## -description

The **PoRegisterForEffectivePowerModeNotifications** function registers a callback to receive effective power mode change notifications.

## -parameters

### -param Version

Supplies the maximum effective power mode version the caller understands. If the effective power mode comes from a later version, it is mapped to a compatible version that is then passed to the callback.

The following values can be passed in:

- EFFECTIVE_POWER_MODE_V1 is available starting with Windows 10, version 1809 and tracks the performance power slider and energy saver states.

- EFFECTIVE_POWER_MODE_V2 is available starting with Windows 10, version 1903 and tracks the performance power slider, battery saver, game mode and windows mixed reality power states.

### -param Callback

A pointer to the callback to call when the effective power mode changes. This will also be called once upon registration to supply the current mode. If multiple callbacks are registered, those callbacks can be called concurrently.

### -param Context

Caller-specified opaque context.

### -param RegistrationHandle

This is a pointer to a variable that receives a handle to the registration. This handle can be used to unregister the callback function.

### -param DeviceObject

This is an optional parameter that, if specified, provides a registered callback (such as from a driver) with the specified device context.

## -returns

Returns **S_OK** (zero) if the call was successful, and a nonzero value if the call failed.

## -remarks

Immediately after registration, the callback will be invoked with the current value of the power setting. If the registration occurs while the power mode is changing, you may receive multiple callbacks. The last callback is the most recent update.

## -see-also

[**PO_EFFECTIVE_POWER_MODE**](ne-wdm-po_effective_power_mode.md)

[PO_EFFECTIVE_POWER_MODE_CALLBACK](nc-wdm-po_effective_power_mode_callback.md)

[PoUnregisterFromEffectivePowerModeNotifications](nf-wdm-pounregisterfromeffectivepowermodenotifications.md)
