---
UID: NF:wdm.ExInitializeFastMutex
title: ExInitializeFastMutex function (wdm.h)
description: The ExInitializeFastMutex routine initializes a fast mutex variable, used to synchronize mutually exclusive access by a set of threads to a shared resource.
old-location: kernel\exinitializefastmutex.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExInitializeFastMutex function"]
ms.keywords: ExInitializeFastMutex, ExInitializeFastMutex routine [Kernel-Mode Driver Architecture], k102_b340d108-2e1c-4fa5-9bd0-d174452b125c.xml, kernel.exinitializefastmutex, wdm/ExInitializeFastMutex
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExInitializeFastMutex
 - wdm/ExInitializeFastMutex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExInitializeFastMutex
---

# ExInitializeFastMutex function


## -description

The <b>ExInitializeFastMutex</b> routine initializes a fast mutex variable, used to synchronize mutually exclusive access by a set of threads to a shared resource.

## -parameters

### -param FastMutex 

[out]
A pointer to a caller-allocated <a href="/windows-hardware/drivers/kernel/eprocess">FAST_MUTEX</a> structure, which represents the fast mutex, in the nonpaged memory pool. The allocation must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.

## -remarks

<b>ExInitializeFastMutex</b> must be called before any calls to other <b>Ex<i>Xxx</i>FastMutex</b> routines occur. 

Although the caller supplies the storage for the given fast mutex, the <b>FAST_MUTEX</b> structure is opaque: that is, its members are reserved for system use. 

For better performance, use the <b>Ex<i>Xxx</i>FastMutex</b> routines instead of the <b>Ke<i>Xxx</i>Mutex</b> routines. However, a fast mutex cannot be acquired recursively, as a kernel mutex can. 

For more information about fast mutexes, see <a href="/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes">Fast Mutexes and Guarded Mutexes</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff544337(v=vs.85)">ExAcquireFastMutex</a>



<a href="/previous-versions/windows/hardware/drivers/ff544340(v=vs.85)">ExAcquireFastMutexUnsafe</a>



<a href="/previous-versions/windows/hardware/drivers/ff545549(v=vs.85)">ExReleaseFastMutex</a>



<a href="/previous-versions/windows/hardware/drivers/ff545567(v=vs.85)">ExReleaseFastMutexUnsafe</a>



<a href="/previous-versions/windows/hardware/drivers/ff545647(v=vs.85)">ExTryToAcquireFastMutex</a>



<a href="/windows-hardware/drivers/kernel/eprocess">FAST_MUTEX</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializemutex">KeInitializeMutex</a>
