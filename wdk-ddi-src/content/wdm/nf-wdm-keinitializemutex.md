---
UID: NF:wdm.KeInitializeMutex
title: KeInitializeMutex function
author: windows-driver-content
description: The KeInitializeMutex routine initializes a mutex object, setting it to a signaled state.
old-location: kernel\keinitializemutex.htm
old-project: kernel
ms.assetid: dca6c4a7-66e0-4bdd-9fdd-a32d49836980
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeInitializeMutex routine [Kernel-Mode Driver Architecture], kernel.keinitializemutex, wdm/KeInitializeMutex, k105_0e268ff3-6e9d-41ab-acfd-0bb71e973115.xml, KeInitializeMutex
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeInitializeMutex
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInitializeMutex function


## -description


The <b>KeInitializeMutex</b> routine initializes a mutex object, setting it to a signaled state.


## -syntax


````
VOID KeInitializeMutex(
  _Out_ PRKMUTEX Mutex,
  _In_  ULONG    Level
);
````


## -parameters




#### - Mutex [out]

Pointer to a mutex object, for which the caller provides the storage. The storage must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.


#### - Level [in]

Reserved. Drivers set this to zero.


## -returns


None



## -remarks


For better performance, use fast mutexes or guarded mutexes. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540595">Alternatives to Mutex Objects</a>. 

The mutex object is initialized with an initial state of signaled. 

Storage for a mutex object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

For more information about mutex objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556417">Mutex Objects</a>. 



## -see-also

<a href="..\wdm\nf-wdm-kereadstatemutex.md">KeReadStateMutex</a>

<a href="..\wdm\nf-wdm-exinitializefastmutex.md">ExInitializeFastMutex</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>

<a href="..\wdm\nf-wdm-kereleasemutex.md">KeReleaseMutex</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInitializeMutex routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

