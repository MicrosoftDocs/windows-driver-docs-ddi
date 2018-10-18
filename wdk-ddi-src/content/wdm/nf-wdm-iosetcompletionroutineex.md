---
UID: NF:wdm.IoSetCompletionRoutineEx
title: IoSetCompletionRoutineEx function
author: windows-driver-content
description: The IoSetCompletionRoutineEx routine registers an IoCompletion routine, which is called when the next-lower-level driver has completed the requested operation for the given IRP.
old-location: kernel\iosetcompletionroutineex.htm
tech.root: kernel
ms.assetid: fe84e542-c8b2-4631-9ffb-dde471311871
ms.date: 4/30/2018
ms.keywords: IoSetCompletionRoutineEx, IoSetCompletionRoutineEx routine [Kernel-Mode Driver Architecture], k104_b574c1f0-f1e7-4c34-93ee-4681ec9e1046.xml, kernel.iosetcompletionroutineex, wdm/IoSetCompletionRoutineEx
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompleteRequest, CompleteRequestStatusCheck, CompletionRoutineRegistered, IoAllocateForward, IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildFsdForward, IoBuildFsdIrpSignalEventInCompletion, IoBuildFsdIrpSignalEventInCompletion2, IoBuildFsdIrpSignalEventInCompletion3, IoBuildFsdIrpSignalEventInCompletionTimeout, IoSetCompletionExCompleteIrp, IoSetCompletionRoutineExCheck, IoSetCompletionRoutineExCheckDeviceObject, LowerDriverReturn, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequestEx, SignalEventInCompletion, SignalEventInCompletion2, SignalEventInCompletion3, StartDeviceWait2, StartDeviceWait4, SetCompletionRoutineFromDispatch, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoSetCompletionRoutineEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetCompletionRoutineEx function


## -description


The <b>IoSetCompletionRoutineEx</b> routine registers an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine, which is called when the next-lower-level driver has completed the requested operation for the given IRP.


## -parameters




### -param DeviceObject [in]

Pointer to the driver's device object.


### -param Irp [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> that the driver is processing.


### -param CompletionRoutine [in]

Specifies the entry point for the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine, which is called when the next-lower driver completes the packet.


### -param Context [in, optional]

Pointer to a driver-determined context to pass to the <i>IoCompletion</i> routine. Context information must be stored in nonpaged memory, because the <i>IoCompletion</i> routine is called at IRQL &lt;= DISPATCH_LEVEL.


### -param InvokeOnSuccess [in]

Specifies whether the completion routine is called if the IRP is completed with a success status value in the IRP's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure, based on results of the NT_SUCCESS macro (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS values</a>).


### -param InvokeOnError [in]

Specifies whether the completion routine is called if the IRP is completed with a nonsuccess status value in the IRP's <b>IO_STATUS_BLOCK</b> structure.


### -param InvokeOnCancel [in]

Specifies whether the completion routine is called if a driver or the kernel has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548338">IoCancelIrp</a> to cancel the IRP.


## -returns



This routine returns STATUS_SUCCESS on success, or STATUS_INSUFFICIENT_RESOURCES if insufficient memory is available for the operation.




## -remarks



<div class="alert"><b>Note</b>  Unlike <a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>, the <b>IoSetCompletionRoutineEx</b> routine returns an NTSTATUS value. The driver must check this value to determine if the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine was successfully registered. If the <i>IoCompletion</i> routine is successfully registered, <b>IoSetCompletionRoutineEx</b> allocates memory that remains allocated until the <i>IoCompletion</i> routine executes. Drivers must ensure that their <i>IoCompletion</i> routine executes by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>; otherwise, the kernel will leak memory.</div>
<div> </div>
The <i>IoCompletion</i> routine must belong to the driver that owns the device object pointed to by <i>DeviceObject</i>. This requirement prevents the <i>IoCompletion</i> routine from being unloaded before it returns.

The behavior of <b>IoSetCompletionRoutineEx</b> is the same as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a> routine, except that:

<ul>
<li>
<b>IoSetCompletionRoutineEx</b> guarantees that a non-Plug and Play driver is not unloaded before the <i>IoCompletion</i> routine runs.

</li>
<li>
<b>IoSetCompletionRoutineEx</b> is a routine that returns an NTSTATUS value.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548324">IoBuildPartialMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>
 

 

