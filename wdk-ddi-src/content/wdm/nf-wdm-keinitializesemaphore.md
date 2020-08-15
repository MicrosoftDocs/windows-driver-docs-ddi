---
UID: NF:wdm.KeInitializeSemaphore
title: KeInitializeSemaphore function (wdm.h)
description: The KeInitializeSemaphore routine initializes a semaphore object with a specified count and specifies an upper limit that the count can attain.
old-location: kernel\keinitializesemaphore.htm
tech.root: kernel
ms.assetid: 447a7ba5-8357-4383-987f-51f5b3c9996c
ms.date: 04/30/2018
keywords: ["KeInitializeSemaphore function"]
ms.keywords: KeInitializeSemaphore, KeInitializeSemaphore routine [Kernel-Mode Driver Architecture], k105_a966274e-6afe-4569-ae7c-65dccbb3f1dc.xml, kernel.keinitializesemaphore, wdm/KeInitializeSemaphore
f1_keywords:
 - "wdm/KeInitializeSemaphore"
 - "KeInitializeSemaphore"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeInitializeSemaphore
targetos: Windows
req.typenames: 
---

# KeInitializeSemaphore function


## -description


The <b>KeInitializeSemaphore</b> routine initializes a semaphore object with a specified count and specifies an upper limit that the count can attain.


## -parameters




### -param Semaphore 
[out]
Pointer to a dispatcher object of type semaphore, for which the caller provides the storage.


### -param Count 
[in]
Specifies the initial count value to be assigned to the semaphore. This value must be positive. A nonzero value sets the initial state of the semaphore to signaled.


### -param Limit 
[in]
Specifies the maximum count value that the semaphore can attain. This value must be positive. It determines how many waiting threads become eligible for execution when the semaphore is set to the signaled state and can therefore access the resource that the semaphore protects. 


## -remarks



The semaphore object is initialized with the specified initial count and limit.

Storage for a semaphore object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

For more information about semaphore objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/semaphore-objects">Semaphore Objects</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereadstatesemaphore">KeReadStateSemaphore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasesemaphore">KeReleaseSemaphore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>
 

 

