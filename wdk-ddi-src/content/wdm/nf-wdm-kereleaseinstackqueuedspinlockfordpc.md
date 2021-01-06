---
UID: NF:wdm.KeReleaseInStackQueuedSpinLockForDpc
title: KeReleaseInStackQueuedSpinLockForDpc function (wdm.h)
description: The KeReleaseInStackQueuedSpinLockForDpc routine releases a queued spin lock that was acquired by calling KeAcquireInStackQueuedSpinLockForDpc.
old-location: kernel\kereleaseinstackqueuedspinlockfordpc.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeReleaseInStackQueuedSpinLockForDpc function"]
ms.keywords: KeReleaseInStackQueuedSpinLockForDpc, KeReleaseInStackQueuedSpinLockForDpc routine [Kernel-Mode Driver Architecture], k105_19c82f3d-cecf-4c77-9800-4b80c63db572.xml, kernel.kereleaseinstackqueuedspinlockfordpc, wdm/KeReleaseInStackQueuedSpinLockForDpc
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - KeReleaseInStackQueuedSpinLockForDpc
 - wdm/KeReleaseInStackQueuedSpinLockForDpc
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeReleaseInStackQueuedSpinLockForDpc
---

# KeReleaseInStackQueuedSpinLockForDpc function


## -description

The <b>KeReleaseInStackQueuedSpinLockForDpc</b> routine releases a queued spin lock that was acquired by calling <a href="/previous-versions/windows/hardware/drivers/ff551912(v=vs.85)">KeAcquireInStackQueuedSpinLockForDpc</a>.

## -parameters

### -param LockHandle 

[in]
Pointer to the <a href="/windows-hardware/drivers/kernel/eprocess">KLOCK_QUEUE_HANDLE</a> structure that <a href="/previous-versions/windows/hardware/drivers/ff551912(v=vs.85)">KeAcquireInStackQueuedSpinLockForDpc</a> initialized when the queued spin lock was acquired.

## -remarks

For more information about queued spin locks, see <a href="/windows-hardware/drivers/kernel/queued-spin-locks">Queued Spin Locks</a>.

If the current IRQL was PASSIVE_LEVEL when the queued spin lock was acquired, <b>KeReleaseSpinLockForDpc</b> lowers the current IRQL to PASSIVE_LEVEL. If the current IRQL was DISPATCH_LEVEL when the queued spin lock was acquired, <b>KeReleaseSpinLockForDpc</b> does not change the current IRQL.

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">KLOCK_QUEUE_HANDLE</a>



<a href="/previous-versions/windows/hardware/drivers/ff551912(v=vs.85)">KeAcquireInStackQueuedSpinLockForDpc</a>
