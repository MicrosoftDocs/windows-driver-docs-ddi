---
UID: NF:wdm.KeReleaseSpinLockFromDpcLevel~r1
title: KeReleaseSpinLockFromDpcLevel macro (wdm.h)
description: The KeReleaseSpinLockFromDpcLevel routine releases an executive spin lock without changing the IRQL.
old-location: kernel\kereleasespinlockfromdpclevel.htm
tech.root: kernel
ms.assetid: 5f7a92ee-ebaf-442f-a197-2fb58dd65a25
ms.date: 04/30/2018
keywords: ["KeReleaseSpinLockFromDpcLevel macro"]
ms.keywords: KeReleaseSpinLockFromDpcLevel, KeReleaseSpinLockFromDpcLevel routine [Kernel-Mode Driver Architecture], KefReleaseSpinLockFromDpcLevel, k105_ed15a49d-6903-4f9f-914c-668242701b1e.xml, kernel.kereleasespinlockfromdpclevel, wdm/KeReleaseSpinLockFromDpcLevel, wdm/KefReleaseSpinLockFromDpcLevel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs, IrqlDispatch, SpinLockSafe
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeReleaseSpinLockFromDpcLevel
 - wdm/KeReleaseSpinLockFromDpcLevel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeReleaseSpinLockFromDpcLevel
 - KefReleaseSpinLockFromDpcLevel
---

# KeReleaseSpinLockFromDpcLevel macro


## -description

The <b>KeReleaseSpinLockFromDpcLevel</b> routine releases an executive spin lock without changing the IRQL.

## -parameters

### -param SpinLock 

[in, out]
Pointer to an executive KSPIN_LOCK spin lock for which the caller provides the storage.

## -remarks

Drivers call <b>KeReleaseSpinLockFromDpcLevel</b> to release a spin lock acquired by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlockatdpclevel">KeAcquireSpinLockAtDpcLevel</a>.

It is an error to call <b>KeReleaseSpinLockFromDpcLevel</b> if the specified spin lock was acquired by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a> because the caller's original IRQL is not restored, which can cause deadlocks or fatal page faults.

For more information about spin locks, see <a href="/windows-hardware/drivers/kernel/spin-locks">Spin Locks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlockatdpclevel">KeAcquireSpinLockAtDpcLevel</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlock">KeReleaseSpinLock</a>