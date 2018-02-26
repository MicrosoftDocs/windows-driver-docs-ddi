---
UID: NF:wdm.ExInitializeFastMutex
title: ExInitializeFastMutex function
author: windows-driver-content
description: The ExInitializeFastMutex routine initializes a fast mutex variable, used to synchronize mutually exclusive access by a set of threads to a shared resource.
old-location: kernel\exinitializefastmutex.htm
old-project: kernel
ms.assetid: edd189f9-1089-470f-95a9-670bdba9c210
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , E, ExInitializeFastMutex, ExInitializeFastMutex routine [Kernel-Mode Driver Architecture], F, I, M, a, e, i, k102_b340d108-2e1c-4fa5-9bd0-d174452b125c.xml, kernel.exinitializefastmutex, l, n, s, t, u, wdm/ExInitializeFastMutex, x, z"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExInitializeFastMutex
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExInitializeFastMutex function


## -description


The <b>ExInitializeFastMutex</b> routine initializes a fast mutex variable, used to synchronize mutually exclusive access by a set of threads to a shared resource.


## -syntax


````
VOID ExInitializeFastMutex(
  _Out_ PFAST_MUTEX FastMutex
);
````


## -parameters




### -param FastMutex [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff545715">FAST_MUTEX</a> structure, which represents the fast mutex, in the nonpaged memory pool. The allocation must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.


## -returns



None




## -remarks



<b>ExInitializeFastMutex</b> must be called before any calls to other <b>Ex<i>Xxx</i>FastMutex</b> routines occur. 

Although the caller supplies the storage for the given fast mutex, the <b>FAST_MUTEX</b> structure is opaque: that is, its members are reserved for system use. 

For better performance, use the <b>Ex<i>Xxx</i>FastMutex</b> routines instead of the <b>Ke<i>Xxx</i>Mutex</b> routines. However, a fast mutex cannot be acquired recursively, as a kernel mutex can. 

For more information about fast mutexes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545716">Fast Mutexes and Guarded Mutexes</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545647">ExTryToAcquireFastMutex</a>



<a href="..\wdm\nf-wdm-keinitializemutex.md">KeInitializeMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545567">ExReleaseFastMutexUnsafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545715">FAST_MUTEX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544340">ExAcquireFastMutexUnsafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544337">ExAcquireFastMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545549">ExReleaseFastMutex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInitializeFastMutex routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

