---
UID: NF:wdm.ExCancelTimer
title: ExCancelTimer function (wdm.h)
description: The ExCancelTimer routine cancels a timer that was set by a previous call to the ExSetTimer routine.
old-location: kernel\excanceltimer.htm
tech.root: kernel
ms.assetid: 5E52550D-0A81-4C72-9A82-7C13BC3EFE00
ms.date: 04/30/2018
keywords: ["ExCancelTimer function"]
ms.keywords: ExCancelTimer, ExCancelTimer routine [Kernel-Mode Driver Architecture], kernel.excanceltimer, wdm/ExCancelTimer
f1_keywords:
 - "wdm/ExCancelTimer"
 - "ExCancelTimer"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ntoskrnl.lib
- ntoskrnl.dll
api_name:
- ExCancelTimer
targetos: Windows
req.typenames: 
---

# ExCancelTimer function


## -description


The <b>ExCancelTimer</b> routine cancels a timer that was set by a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsettimer">ExSetTimer</a> routine.


## -parameters




### -param Timer [in, out]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a> structure. This structure is a timer object that was previously allocated by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatetimer">ExAllocateTimer</a> routine.


### -param Parameters [in, optional]

Drivers must set this parameter to <b>NULL</b>.


## -returns



This routine returns <b>TRUE</b> if the timer was canceled. Otherwise, the routine returns <b>FALSE</b>.




## -remarks



After your driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsettimer">ExSetTimer</a> routine to set the timer, the timer might be canceled before it expires. The driver can call the <b>ExCancelTimer</b> routine to explicitly cancel a pending timer. Also, if the driver calls the <b>ExSetTimer</b> routine to set a new timer on a timer object before a previously set timer on this object expires, this <b>ExSetTimer</b> call implicitly cancels the previous timer and then starts the new timer.

A return value of <b>TRUE</b> indicates that the timer was set when <b>ExCancelTimer</b> was called. In this case, the routine cancels the timer. A return value of <b>FALSE</b> indicates that the timer was not set, which might mean that the timer was never set, that the timer had already been canceled, or that the timer had already expired.

When a timer expires, the operating system signals the timer object. As an option, a driver can supply an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ext_callback">ExTimerCallback</a> callback routine that is called when the timer expires. If the driver supplies this callback routine, this routine is guaranteed to be called if the timer object is signaled. If the timer is canceled before it expires, the timer object is not signaled and the callback routine is not called.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">ExXxxTimer Routines and EX_TIMER Objects</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatetimer">ExAllocateTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsettimer">ExSetTimer</a>
 

 

