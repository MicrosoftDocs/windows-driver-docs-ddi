---
UID: NF:wdm.KeReleaseGuardedMutexUnsafe
title: KeReleaseGuardedMutexUnsafe function
author: windows-driver-content
description: The KeReleaseGuardedMutexUnsafe routine releases a guarded mutex acquired by KeAcquireGuardedMutexUnsafe.
old-location: kernel\kereleaseguardedmutexunsafe.htm
old-project: kernel
ms.assetid: 710f289c-4c2a-4ad3-b5af-ad8d8ca123a3
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeReleaseGuardedMutexUnsafe, KeReleaseGuardedMutexUnsafe routine [Kernel-Mode Driver Architecture], k105_645b087e-53ee-4434-ae8b-2bb801d1217e.xml, kernel.kereleaseguardedmutexunsafe, wdm/KeReleaseGuardedMutexUnsafe
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeReleaseGuardedMutexUnsafe
product: Windows
targetos: Windows
req.typenames: 
---

# KeReleaseGuardedMutexUnsafe function


## -description


The <b>KeReleaseGuardedMutexUnsafe</b> routine releases a guarded mutex acquired by <a href="https://msdn.microsoft.com/library/windows/hardware/ff551894">KeAcquireGuardedMutexUnsafe</a>.


## -parameters




### -param FastMutex [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554235">KGUARDED_MUTEX</a> structure for the guarded mutex.


## -returns



None




## -remarks



For more information about guarded mutexes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545716">Fast Mutexes and Guarded Mutexes</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551894">KeAcquireGuardedMutexUnsafe</a>
 

 

