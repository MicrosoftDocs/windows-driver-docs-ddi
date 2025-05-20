---
UID: NF:wdm.KfAcquireSpinLock
tech.root: kernel
title: KfAcquireSpinLock
ms.date: 05/20/2025
targetos: Windows
description: The KfAcquireSpinLock routine acquires a spin lock so the caller can synchronize access to shared data in a multiprocessor-safe way by raising IRQL.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: hal.dll
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
 - KfAcquireSpinLock
f1_keywords:
 - KfAcquireSpinLock
 - wdm/KfAcquireSpinLock
dev_langs:
 - c++
helpviewer_keywords:
 - KfAcquireSpinLock
---

## -description

The **KfAcquireSpinLock** routine acquires a spin lock so the caller can synchronize access to shared data in a multiprocessor-safe way by raising IRQL.

## -parameters

### -param SpinLock

Pointer to an initialized KSPIN_LOCK spin lock for which the caller provides the storage.

## -returns

## -remarks

For more information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/spin-locks).

## -see-also

- **[KeAcquireSpinLock](nf-wdm-keacquirespinlock.md)**
- **[KeInitializeSpinLock](nf-wdm-keinitializespinlock.md)**
- **[KeReleaseSpinLock](nf-wdm-kereleasespinlock.md)**
- **[KfReleaseSpinLock](nf-wdm-kfreleasespinlock.md)**
- [Spin Locks](/windows-hardware/drivers/kernel/spin-locks)
