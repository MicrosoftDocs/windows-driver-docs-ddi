---
UID: NF:wdm.KeInitializeTimer
title: KeInitializeTimer function (wdm.h)
description: The KeInitializeTimer routine initializes a timer object.
old-location: kernel\keinitializetimer.htm
tech.root: kernel
ms.assetid: 97140cf6-9c5a-4fdc-b7c7-10e6d28b9b1b
ms.date: 04/30/2018
keywords: ["KeInitializeTimer function"]
ms.keywords: KeInitializeTimer, KeInitializeTimer routine [Kernel-Mode Driver Architecture], k105_ce90de5c-7259-4863-adf1-fe90f288e791.xml, kernel.keinitializetimer, wdm/KeInitializeTimer
f1_keywords:
 - "wdm/KeInitializeTimer"
 - "KeInitializeTimer"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeInitializeTimer
targetos: Windows
req.typenames: 
---

# KeInitializeTimer function


## -description


The <b>KeInitializeTimer</b> routine initializes a timer object.


## -parameters




### -param Timer 
[out]
Pointer to a timer object, for which the caller provides the storage.


## -remarks



The timer object is initialized to a not-signaled state.

Storage for a timer object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

<b>KeInitializeTimer</b> can only initialize a notification timer. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimerex">KeInitializeTimerEx</a> to initialize a notification timer or a synchronization timer.

Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimer">KeSetTimer</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a> to define when the timer will expire.

For more information about timer objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/timer-objects-and-dpcs">Timer Objects and DPCs</a>.

Callers of <b>KeInitializeTimer</b> should be running at IRQL = DISPATCH_LEVEL or lower. It is best to initialize timers at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kecanceltimer">KeCancelTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimerex">KeInitializeTimerEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereadstatetimer">KeReadStateTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimer">KeSetTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>
 

 

