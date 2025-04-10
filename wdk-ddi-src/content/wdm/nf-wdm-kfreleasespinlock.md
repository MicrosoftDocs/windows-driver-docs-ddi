---
UID: NF:wdm.KfReleaseSpinLock
tech.root: kernel
title: KfReleaseSpinLock
ms.date: 04/10/2025
targetos: Windows
description: The KfReleaseSpinLock routine releases a spin lock and restores the original IRQL at which the caller was running.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
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
 - KfReleaseSpinLock
f1_keywords:
 - KfReleaseSpinLock
 - wdm/KfReleaseSpinLock
dev_langs:
 - c++
helpviewer_keywords:
 - KfReleaseSpinLock
---

## -description

The **KfReleaseSpinLock** routine releases a spin lock and restores the original IRQL at which the caller was running.

## -parameters

### -param SpinLock

Pointer to a KSPIN_LOCK spin lock for which the caller provides the storage.

### -param NewIrql

Specifies the KIRQL value saved from the preceding call to [**KfAcquireSpinLock**](nf-wdm-kfacquirespinlock.md).

## -remarks

For more information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/spin-locks).

## -see-also

[**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md)

[**KeInitializeSpinLock**](nf-wdm-keinitializespinlock)

[**KeReleaseSpinLock**](nf-wdm-kereleasespinlock.md)

[**KfAcquireSpinLock**](nf-wdm-kfacquirespinlock.md)

[Spin Locks](/windows-hardware/drivers/kernel/spin-locks)
