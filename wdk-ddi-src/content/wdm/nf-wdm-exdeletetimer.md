---
UID: NF:wdm.ExDeleteTimer
title: ExDeleteTimer function (wdm.h)
description: The ExDeleteTimer routine deletes a timer object that was previously allocated by the ExAllocateTimer routine.
old-location: kernel\exdeletetimer.htm
tech.root: kernel
ms.assetid: CE0C1D49-1505-464E-90DB-2C6D30C04EC1
ms.date: 04/30/2018
ms.keywords: ExDeleteTimer, ExDeleteTimer routine [Kernel-Mode Driver Architecture], kernel.exdeletetimer, wdm/ExDeleteTimer
ms.topic: function
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
req.irql: See Remarks.
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ntoskrnl.lib
- ntoskrnl.dll
api_name:
- ExDeleteTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExDeleteTimer function


## -description


The <b>ExDeleteTimer</b> routine deletes a timer object that was previously allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a> routine.


## -parameters




### -param Timer [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a> structure. This structure is a timer object that was previously allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a> routine.


### -param Cancel [in]

Whether to cancel the timer if it is currently set. If <b>TRUE</b>, the routine cancels the timer if the timer is set. If <b>FALSE</b>, the routine does not cancel the timer if it is set. If the caller sets <i>Wait</i> to <b>TRUE</b>, <i>Cancel</i> must also be <b>TRUE</b>; otherwise, a bug check occurs.


### -param Wait [in]

Whether to wait for the timer to finish expiring if the timer has already started the process of expiring. If <b>TRUE</b>, the routine waits for the timer to expire. If <b>FALSE</b>, the routine does not wait. For more information, see Remarks.


### -param Parameters [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265194">EXT_DELETE_PARAMETERS</a> structure. The calling driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265182">ExInitializeDeleteTimerParameters</a> routine to initialize this structure.


## -returns



This routine returns <b>TRUE</b> if <i>Cancel</i> is <b>TRUE</b> and the timer was canceled. Otherwise, the routine returns <b>FALSE</b>. For more information, see Remarks.




## -remarks



After your driver calls this routine, the timer object pointed to by <i>Timer</i> might no longer be valid. However, the <i>Timer</i> parameter value passed to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265190">ExTimerCallback</a> callback routine, if the driver implements this routine, is always a valid pointer to a timer object.

If <i>Cancel</i> is <b>TRUE</b>, a return value of <b>FALSE</b> indicates that the timer was never set, or that the timer was set but expired before it could be canceled.  If <i>Cancel</i> is <b>FALSE</b>, the routine always returns <b>FALSE</b>.

This routine can block if <i>Wait</i> is <b>TRUE</b>. If <b>ExDeleteTimer</b> is called from the driver's <i>ExTimerCallback</i> routine, which is called at DISPATCH_LEVEL, the <i>Wait</i> parameter in this call must be <b>FALSE</b>.

If <i>Wait</i> is <b>TRUE</b>, the routine must be called at IRQL <= APC_LEVEL. If <i>Wait</i> is <b>FALSE</b>, the routine can be called at IRQL <= DISPATCH_LEVEL.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265175">Deleting a System-Allocated Timer Object</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265194">EXT_DELETE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265182">ExInitializeDeleteTimerParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265190">ExTimerCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265192">ExTimerDeleteCallback</a>
 

 

