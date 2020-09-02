---
UID: NF:storport.StorPortAcquireSpinLock
title: StorPortAcquireSpinLock function (storport.h)
description: The StorPortAcquireSpinLock routine acquires the specified spin lock.
old-location: storage\storportacquirespinlock.htm
tech.root: storage
ms.assetid: 52a877c7-b274-4bec-b948-edb0585a09e1
ms.date: 03/29/2018
keywords: ["StorPortAcquireSpinLock function"]
ms.keywords: StorPortAcquireSpinLock, StorPortAcquireSpinLock routine [Storage Devices], storage.storportacquirespinlock, storport/StorPortAcquireSpinLock, storprt_a5092ef5-d8ab-4175-8799-df23cfcd4dc8.xml
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortAcquireSpinLock
 - storport/StorPortAcquireSpinLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortAcquireSpinLock
---

# StorPortAcquireSpinLock function


## -description

The **StorPortAcquireSpinLock** routine acquires the specified spin lock.

## -parameters

### -param DeviceExtension 

[in]
A pointer to the miniport driver per-adapter device extension.

### -param SpinLock 

[in]
Contains an enumerator value of type [**STOR_SPINLOCK**](ne-storport-_stor_spinlock.md) that specifies the spin lock to acquire.

### -param LockContext 

[in]
A pointer to the DPC object for which the lock is held if *SpinLock* indicates a type of **DpcLock**. This member should be **NULL** if *SpinLock* indicates a type of either **InterruptLock** or **StartIoLock**.

### -param LockHandle 

[in, out]
A pointer to a buffer that, on return, will contain a lock handle. To release the lock, the caller must pass this handle to the [**StorPortReleaseSpinLock**](nf-storport-storportreleasespinlock.md) routine.

## -remarks

Miniport drivers must ensure that they do not attempt to acquire a lock that is already held or acquire locks in an incorrect order. Either of these mistakes will result in system deadlock.

Certain locks are held automatically by the port driver before it calls the miniport driver callback routines. For each miniport driver callback routine, the following table indicates which locks the port driver acquires automatically before calling the callback routine.

| Miniport driver routine | Spin lock held by port driver |
| ----------------------- | ----------------------------- |
| [**HwStorFindAdapter**](nc-storport-hw_find_adapter.md) | None |
| [**HwStorInitialize**](nc-storport-hw_initialize.md) | Interrupt (physical miniports), None (virtual miniports) |
| [**HwStorInterrupt**](nc-storport-hw_interrupt.md) | Interrupt |
| [**HwMSIInterruptRoutine**](nc-storport-hw_message_signaled_interrupt_routine.md) | Interrupt |
| [**HwStorStartIo**](nc-storport-hw_startio.md) | StartIo (physical miniports only when requested concurrent channels <= 1) |
| [**HwStorBuildIo**](nc-storport-hw_buildio.md) | None |
| [**HwStorTimer**](nc-storport-hw_timer.md) | Startio, Interrupt (when **SynchronizationModel** member of [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) is set to **StorSynchronizeHalfDuplex**) |
| [**HwStorResetBus**](nc-storport-hw_reset_bus.md) | Startio, Interrupt (when **SynchronizationModel** member of [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) is set to **StorSynchronizeHalfDuplex**) |
| [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) | None. (In Windows Server 2003, the StartIo spin lock was held when control type is ScsiStopAdapter.) |
| [**HwStorUnitControl**](nc-storport-hw_unit_control.md) | None |
| [**HwStorTracingEnabled**](nc-storport-hw_tracing_enabled.md) | None |
| [**HwStorPassiveInitializeRoutine**](nc-storport-hw_passive_initialize_routine.md) | None || [**HwStorDpcRoutine**](nc-storport-hw_dpc_routine.md) | None |
| [**HwStorStateChange**](nc-storport-hw_state_change.md) | Startio, Interrupt (when **SynchronizationModel** member of [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) is set to **StorSynchronizeHalfDuplex**) |

The locks held by the port driver influence which locks the callback routines are allowed to acquire, because spin locks must be acquired in the following order:

* DPC or StartIo
* Interrupt

For instance, if the port driver acquires the *Interrupt* spin lock before calling a callback routine, that callback routine can no longer acquire the *DPC* or *StartIo* spin lock because the *DPC* and *StartIo* spin locks are of a lower order than the *Interrupt* spin lock. On the other hand, if the port driver acquires the *StartIo* spin lock before calling a callback routine, that callback routine, when executed, could still acquire an  *Interrupt* or a *DPC* spin lock.

The following table indicates which spin locks each miniport driver routine can acquire. In those cases where the miniport driver routine must obtain both the *StartIo* spin lock and the *Interrupt* spin lock, the routine must always acquire the *StartIo* spin lock first.

| Miniport driver routine | Allowed spin locks |
| ----------------------- | ------------------ |
| [**HwStorFindAdapter**](nc-storport-hw_find_adapter.md) | None |
| [**HwStorInitialize**](nc-storport-hw_initialize.md)  | None |
| [**HwStorInterrupt**](nc-storport-hw_interrupt.md)    | None |
| [**HwMSIInterruptRoutine**](nc-storport-hw_message_signaled_interrupt_routine.md) | None |
| [**HwStorStartIo**](nc-storport-hw_startio.md) | DPC, Interrupt. Note that StartIo can be acquired in a virtual miniport driver or from a physical miniport driver that uses multiple concurrent channels. |
| [**HwStorBuildIo**](nc-storport-hw_buildio.md) |DPC, StartIo, Interrupt |
| [**HwStorTimer**](nc-storport-hw_timer.md) | Interrupt (when **SynchronizationModel** member of [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) is not set to **StorSynchronizeHalfDuplex**) |
| [**HwStorResetBus**](nc-storport-hw_reset_bus.md) | Interrupt (when **SynchronizationModel** member of [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) is not set to **StorSynchronizeHalfDuplex**) |
| [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) | DPC, StartIo, Interrupt. (In Windows Server 2003, the no spin lock is allowed when control type is ScsiStopAdapter.) |
| [**HwStorUnitControl**](nc-storport-hw_unit_control.md) | DPC, StartIo, Interrupt |
| [**HwStorTracingEnabled**](nc-storport-hw_tracing_enabled.md) | DPC, StartIo, Interrupt |
| [**HwStorPassiveInitializeRoutine**](nc-storport-hw_passive_initialize_routine.md) | None |
| [**HwStorDpcRoutine**](nc-storport-hw_dpc_routine.md) | DPC, StartIo, Interrupt |
| [**HwStorStateChange**](nc-storport-hw_state_change.md) | Interrupt (when **SynchronizationModel** member of [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) is not set to **StorSynchronizeHalfDuplex**) |

## -see-also

[**STOR_SPINLOCK**](ne-storport-_stor_spinlock.md)

[**StorPortReleaseSpinLock**](nf-storport-storportreleasespinlock.md)

