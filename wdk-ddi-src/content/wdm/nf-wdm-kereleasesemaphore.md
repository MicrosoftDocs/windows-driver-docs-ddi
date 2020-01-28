---
UID: NF:wdm.KeReleaseSemaphore
title: KeReleaseSemaphore function (wdm.h)
description: The KeReleaseSemaphore routine releases the specified semaphore object.
old-location: kernel\kereleasesemaphore.htm
tech.root: kernel
ms.assetid: 357a97e6-cb19-43df-9b90-db199c712878
ms.date: 04/30/2018
ms.keywords: KeReleaseSemaphore, KeReleaseSemaphore routine [Kernel-Mode Driver Architecture], k105_43c9caa4-267a-43c4-8b48-f030e1c2f0d5.xml, kernel.kereleasesemaphore, wdm/KeReleaseSemaphore
f1_keywords:
 - "wdm/KeReleaseSemaphore"
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeReleaseSemaphore
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeReleaseSemaphore function


## -description


The <b>KeReleaseSemaphore</b> routine releases the specified semaphore object. 


## -parameters




### -param Semaphore [in, out]

A pointer to an initialized semaphore object for which the caller provides the storage.


### -param Increment [in]

Specifies the priority increment to be applied if releasing the semaphore causes a wait to be satisfied.


### -param Adjustment [in]

Specifies a value to be added to the current semaphore count. This value must be positive.


### -param Wait [in]

Specifies whether the call to <b>KeReleaseSemaphore</b> is to be followed <u>immediately</u> by a call to one of the <b>KeWait<i>Xxx</i></b> routines. If <b>TRUE</b>, the <b>KeReleaseSemaphore</b> call must be followed by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>. For more information, see the following Remarks section. 


## -returns



If the return value is zero, the previous state of the semaphore object is not-signaled. 




## -remarks



<b>KeReleaseSemaphore</b> supplies a run-time priority boost for waiting threads. If this call sets the semaphore to the signaled state, the semaphore count is augmented by the specified value. The caller can also specify whether it will call one of the <b>KeWait<i>Xxx</i></b> routines as soon as <b>KeReleaseSemaphore</b> returns control.

Releasing a semaphore object causes the semaphore count to be augmented by the value of the <i>Adjustment</i> parameter. If the resulting value is greater than the limit of the semaphore object, the count is not adjusted and an exception, STATUS_SEMAPHORE_LIMIT_EXCEEDED, is raised.

Augmenting the semaphore object count causes the semaphore to attain a signaled state, and an attempt is made to satisfy as many waits as possible on the semaphore object.

The <b>KeReleaseSemaphore</b> routine might temporarily raise the IRQL. If the <i>Wait</i> parameter is <b>FALSE</b>, the routine, before it returns, restores the IRQL to the original value that it had at the start of the call.

If <i>Wait</i> = <b>TRUE</b>, the routine returns without lowering the IRQL. In this case, the <b>KeReleaseSemaphore</b> call must be immediately followed by a <b>KeWait<i>Xxx</i></b> call. By setting <i>Wait</i> = <b>TRUE</b>, the caller can prevent an unnecessary context switch from occurring between the <b>KeReleaseSemaphore</b> call and the <b>KeWait<i>Xxx</i></b> call. The <b>KeWait<i>Xxx</i></b> routine, before it returns, restores the IRQL to its original value at the start of the <b>KeReleaseSemaphore</b> call. Although the IRQL disables context switches between the two calls, these calls cannot reliably be used as the start and end of an atomic operation. For example, between these two calls, a thread that is running at the same time on another processor might change the state of the semaphore object or of the target of the wait.

For more information about semaphore objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/semaphore-objects">Semaphore Objects</a>.

Callers of <b>KeReleaseSemaphore</b> must be running at IRQL <= DISPATCH_LEVEL provided that <i>Wait</i> is set to <b>FALSE</b>. Otherwise, the caller must be running at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializesemaphore">KeInitializeSemaphore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereadstatesemaphore">KeReadStateSemaphore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>
 

 

