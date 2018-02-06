---
UID: NF:storport.StorPortAcquireSpinLock
title: StorPortAcquireSpinLock function
author: windows-driver-content
description: The StorPortAcquireSpinLock routine acquires the specified spin lock.
old-location: storage\storportacquirespinlock.htm
old-project: storage
ms.assetid: 52a877c7-b274-4bec-b948-edb0585a09e1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortAcquireSpinLock, storport/StorPortAcquireSpinLock, storage.storportacquirespinlock, storprt_a5092ef5-d8ab-4175-8799-df23cfcd4dc8.xml, StorPortAcquireSpinLock routine [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortSpinLock, StorPortSpinLock3, StorPortSpinLock4
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortAcquireSpinLock
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortAcquireSpinLock function


## -description


The <b>StorPortAcquireSpinLock</b> routine acquires the specified spin lock. 


## -syntax


````
VOID StorPortAcquireSpinLock(
  _In_    PVOID             DeviceExtension,
  _In_    STOR_SPINLOCK     SpinLock,
  _In_    PVOID             LockContext,
  _Inout_ PSTOR_LOCK_HANDLE LockHandle
);
````


## -parameters




### -param DeviceExtension [in]

A pointer to the miniport driver per-adapter device extension. 


### -param SpinLock [in]

Contains an enumerator value of type <a href="..\storport\ne-storport-_stor_spinlock.md">STOR_SPINLOCK</a> that specifies the spin lock to acquire. 


### -param LockContext [in]

A pointer to the DPC object for which the lock is held if <i>SpinLock</i> indicates a type of <b>DpcLock</b>. This member should be <b>NULL</b> if <i>SpinLock </i>indicates a type of either <b>InterruptLock</b> or <b>StartIoLock</b>. 


### -param LockHandle [in, out]

A pointer to a buffer that, on return, will contain a lock handle. To release the lock, the caller must pass this handle to the <a href="..\storport\nf-storport-storportreleasespinlock.md">StorPortReleaseSpinLock</a> routine. 


## -returns


None



## -remarks


Miniport drivers must ensure that they do not attempt to acquire a lock that is already held or acquire locks in an incorrect order. Either of these mistakes will result in system deadlock.

Certain locks are held automatically by the port driver before it calls the miniport driver callback routines. For each miniport driver callback routine, the following table indicates which locks the port driver acquires automatically before calling the callback routine.
<table>
<tr>
<th>Miniport driver routine</th>
<th>Spin lock held by port driver</th>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a>


</td>
<td>
Interrupt (physical miniports), None (virtual miniports)

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_interrupt.md">HwStorInterrupt</a>


</td>
<td>
Interrupt

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_message_signaled_interrupt_routine.md">HwMSIInterruptRoutine</a>


</td>
<td>
Interrupt

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_startio.md">
        HwStorStartIo</a>


</td>
<td>
StartIo (physical miniports only when requested concurrent channels &lt;= 1)

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_buildio.md">HwStorBuildIo</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_timer.md">HwStorTimer</a>


</td>
<td>
 Startio, Interrupt (when <b>SynchronizationModel</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> is set to <b>StorSynchronizeHalfDuplex</b>)

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_reset_bus.md">HwStorResetBus</a>


</td>
<td>
 Startio, Interrupt (when <b>SynchronizationModel</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> is set to <b>StorSynchronizeHalfDuplex</b>)

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a>


</td>
<td>
None

<div class="alert"><b>Note</b>   In Windows Server 2003, the StartIo spin lock was held when control type is ScsiStopAdapter.</div>
<div> </div>
</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_unit_control.md">HwStorUnitControl</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_tracing_enabled.md">HwStorTracingEnabled</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_passive_initialize_routine.md">HwStorPassiveInitializeRoutine</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_dpc_routine.md">HwStorDpcRoutine</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_dpc_routine.md">HwStorStateChange</a>


</td>
<td>
 Startio, Interrupt (when <b>SynchronizationModel</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> is set to <b>StorSynchronizeHalfDuplex</b>)

</td>
</tr>
</table> 

The locks held by the port driver influence which locks the callback routines are allowed to acquire, because spin locks must be acquired in the following order:
<ul>
<li>
DPC or StartIo

</li>
<li>
Interrupt

</li>
</ul>For instance, if the port driver acquires the <i>Interrupt</i> spin lock before calling a callback routine, that callback routine can no longer acquire the <i>DPC</i> or <i>StartIo</i> spin lock because the <i>DPC</i> and <i>StartIo</i> spin locks are of a lower order than the <i>Interrupt</i> spin lock. On the other hand, if the port driver acquires the <i>StartIo</i> spin lock before calling a callback routine, that callback routine, when executed, could still acquire an  <i>Interrupt</i> or a <i>DPC</i> spin lock.

The following table indicates which spin locks each miniport driver routine can acquire. In those cases where the miniport driver routine must obtain both the <i>StartIo</i> spin lock and the <i>Interrupt</i> spin lock, the routine must always acquire the <i>StartIo</i> spin lock first.
<table>
<tr>
<th>Miniport driver routine</th>
<th>Allowed spin locks</th>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_interrupt.md">HwStorInterrupt</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_message_signaled_interrupt_routine.md">HwMSIInterruptRoutine</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_startio.md">
        HwStorStartIo</a>


</td>
<td>
DPC, Interrupt

<div class="alert"><b>Note</b>   StartIo can be acquired in a virtual miniport driver or from a physical miniport driver that uses multiple concurrent channels.</div>
<div> </div>
</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_buildio.md">HwStorBuildIo</a>


</td>
<td>
DPC, StartIo, Interrupt

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_timer.md">HwStorTimer</a>


</td>
<td>
 Interrupt (when <b>SynchronizationModel</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> is not set to <b>StorSynchronizeHalfDuplex</b>)

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_reset_bus.md">HwStorResetBus</a>


</td>
<td>
 Interrupt (when <b>SynchronizationModel</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> is not set to <b>StorSynchronizeHalfDuplex</b>)

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a>


</td>
<td>
DPC, StartIo, Interrupt

<div class="alert"><b>Note</b>   In Windows Server 2003, the no spin lock is allowed when control type is ScsiStopAdapter.</div>
<div> </div>
</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_unit_control.md">HwStorUnitControl</a>


</td>
<td>
DPC, StartIo, Interrupt

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_tracing_enabled.md">HwStorTracingEnabled</a>


</td>
<td>
DPC, StartIo, Interrupt

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_passive_initialize_routine.md">HwStorPassiveInitializeRoutine</a>


</td>
<td>
None

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_dpc_routine.md">HwStorDpcRoutine</a>


</td>
<td>
DPC, StartIo, Interrupt

</td>
</tr>
<tr>
<td>

<a href="..\storport\nc-storport-hw_dpc_routine.md">HwStorStateChange</a>


</td>
<td>
 Interrupt (when <b>SynchronizationModel</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> is not set to <b>StorSynchronizeHalfDuplex</b>)

</td>
</tr>
</table> 



## -see-also

<a href="..\storport\ne-storport-_stor_spinlock.md">STOR_SPINLOCK</a>

<a href="..\storport\nf-storport-storportreleasespinlock.md">StorPortReleaseSpinLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortAcquireSpinLock routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

