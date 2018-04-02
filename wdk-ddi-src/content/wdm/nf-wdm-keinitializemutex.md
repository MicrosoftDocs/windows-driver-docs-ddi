---
UID: NF:wdm.KeInitializeMutex
title: KeInitializeMutex function
author: windows-driver-content
description: The KeInitializeMutex routine initializes a mutex object, setting it to a signaled state.
old-location: kernel\keinitializemutex.htm
old-project: kernel
ms.assetid: dca6c4a7-66e0-4bdd-9fdd-a32d49836980
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeInitializeMutex, KeInitializeMutex routine [Kernel-Mode Driver Architecture], k105_0e268ff3-6e9d-41ab-acfd-0bb71e973115.xml, kernel.keinitializemutex, wdm/KeInitializeMutex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeInitializeMutex
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInitializeMutex function


## -description


The <b>KeInitializeMutex</b> routine initializes a mutex object, setting it to a signaled state.


## -parameters




### -param Mutex [out]

Pointer to a mutex object, for which the caller provides the storage. The storage must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.


### -param Level [in]

Reserved. Drivers set this to zero.


## -returns



None




## -remarks



For better performance, use fast mutexes or guarded mutexes. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540595">Alternatives to Mutex Objects</a>. 

The mutex object is initialized with an initial state of signaled. 

Storage for a mutex object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

For more information about mutex objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556417">Mutex Objects</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545293">ExInitializeFastMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553094">KeReadStateMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553140">KeReleaseMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553324">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

