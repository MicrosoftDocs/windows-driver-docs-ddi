---
UID: NF:wdm.KeInitializeSemaphore
title: KeInitializeSemaphore function
author: windows-driver-content
description: The KeInitializeSemaphore routine initializes a semaphore object with a specified count and specifies an upper limit that the count can attain.
old-location: kernel\keinitializesemaphore.htm
old-project: kernel
ms.assetid: 447a7ba5-8357-4383-987f-51f5b3c9996c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k105_a966274e-6afe-4569-ae7c-65dccbb3f1dc.xml, kernel.keinitializesemaphore, KeInitializeSemaphore, KeInitializeSemaphore routine [Kernel-Mode Driver Architecture], wdm/KeInitializeSemaphore
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
req.ddi-compliance: IrqlKeDispatchLte, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeInitializeSemaphore
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInitializeSemaphore function


## -description


The <b>KeInitializeSemaphore</b> routine initializes a semaphore object with a specified count and specifies an upper limit that the count can attain.


## -syntax


````
VOID KeInitializeSemaphore(
  _Out_ PRKSEMAPHORE Semaphore,
  _In_  LONG         Count,
  _In_  LONG         Limit
);
````


## -parameters




### -param Semaphore [out]

Pointer to a dispatcher object of type semaphore, for which the caller provides the storage.


### -param Count [in]

Specifies the initial count value to be assigned to the semaphore. This value must be positive. A nonzero value sets the initial state of the semaphore to signaled.


### -param Limit [in]

Specifies the maximum count value that the semaphore can attain. This value must be positive. It determines how many waiting threads become eligible for execution when the semaphore is set to the signaled state and can therefore access the resource that the semaphore protects. 


## -returns


None



## -remarks


The semaphore object is initialized with the specified initial count and limit.

Storage for a semaphore object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

For more information about semaphore objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563719">Semaphore Objects</a>. 



## -see-also

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>

<a href="..\wdm\nf-wdm-kereleasesemaphore.md">KeReleaseSemaphore</a>

<a href="..\wdm\nf-wdm-kereadstatesemaphore.md">KeReadStateSemaphore</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInitializeSemaphore routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

