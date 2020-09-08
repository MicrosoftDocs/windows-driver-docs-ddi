---
UID: NF:wdm.KeReleaseGuardedMutexUnsafe
title: KeReleaseGuardedMutexUnsafe function (wdm.h)
description: The KeReleaseGuardedMutexUnsafe routine releases a guarded mutex acquired by KeAcquireGuardedMutexUnsafe.
old-location: kernel\kereleaseguardedmutexunsafe.htm
tech.root: kernel
ms.assetid: 710f289c-4c2a-4ad3-b5af-ad8d8ca123a3
ms.date: 04/30/2018
keywords: ["KeReleaseGuardedMutexUnsafe function"]
ms.keywords: KeReleaseGuardedMutexUnsafe, KeReleaseGuardedMutexUnsafe routine [Kernel-Mode Driver Architecture], k105_645b087e-53ee-4434-ae8b-2bb801d1217e.xml, kernel.kereleaseguardedmutexunsafe, wdm/KeReleaseGuardedMutexUnsafe
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeApcLte1, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - KeReleaseGuardedMutexUnsafe
 - wdm/KeReleaseGuardedMutexUnsafe
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeReleaseGuardedMutexUnsafe
---

# KeReleaseGuardedMutexUnsafe function


## -description

The <b>KeReleaseGuardedMutexUnsafe</b> routine releases a guarded mutex acquired by <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551894(v=vs.85)">KeAcquireGuardedMutexUnsafe</a>.

## -parameters

### -param FastMutex 

[in, out]
Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KGUARDED_MUTEX</a> structure for the guarded mutex.

## -remarks

For more information about guarded mutexes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes">Fast Mutexes and Guarded Mutexes</a>.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551894(v=vs.85)">KeAcquireGuardedMutexUnsafe</a>

