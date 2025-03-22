---
UID: NC:wdm.PO_EFFECTIVE_POWER_MODE_CALLBACK
tech.root: kernel
title: PO_EFFECTIVE_POWER_MODE_CALLBACK (wdm.h)
ms.date: 03/04/2024
targetos: Windows
description: The PO_EFFECTIVE_POWER_MODE_CALLBACK is the effective power mode callback.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: 
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
 - LibDef
api_location:
 - wdm.h
api_name:
 - PO_EFFECTIVE_POWER_MODE_CALLBACK
f1_keywords:
 - PO_EFFECTIVE_POWER_MODE_CALLBACK
 - wdm/PO_EFFECTIVE_POWER_MODE_CALLBACK
dev_langs:
 - c++
helpviewer_keywords:
 - PO_EFFECTIVE_POWER_MODE_CALLBACK
---

# PO_EFFECTIVE_POWER_MODE_CALLBACK function (wdm.h)

## -description

The **PO_EFFECTIVE_POWER_MODE_CALLBACK** is the effective power mode callback.

## -parameters

### -param Mode

Indicates the effective power mode the system is running in. For more information, see [**PO_EFFECTIVE_POWER_MODE**](ne-wdm-po_effective_power_mode.md).

### -param Context

User-specified opaque context. This context would have been passed in at registration in [PoRegisterForEffectivePowerModeNotifications](nf-wdm-poregisterforeffectivepowermodenotifications.md).

## -remarks

Immediately after registration, this callback is invoked with the current value of the power setting. If the registration occurs while the power setting is changing, you may receive multiple callbacks. The last callback is the most recent update.

## -see-also

[**PO_EFFECTIVE_POWER_MODE**](ne-wdm-po_effective_power_mode.md)

[PoRegisterForEffectivePowerModeNotifications](nf-wdm-poregisterforeffectivepowermodenotifications.md)

[PoUnregisterFromEffectivePowerModeNotifications](nf-wdm-pounregisterfromeffectivepowermodenotifications.md)
