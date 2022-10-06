---
UID: NF:wdm.KeAcquireInterruptSpinLock
tech.root: kernel
title: KeAcquireInterruptSpinLock
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the KeAcquireInterruptSpinLock routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: <= DIRQL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DLLExport
api_location:
 - wdm.h
api_name:
 - KeAcquireInterruptSpinLock
f1_keywords:
 - KeAcquireInterruptSpinLock
 - wdm/KeAcquireInterruptSpinLock
dev_langs:
 - c++
helpviewer_keywords:
 - KeAcquireInterruptSpinLock
---

## -description

The **KeAcquireInterruptSpinLock** routine acquires the spin lock associated with an interrupt object.

## -parameters

### -param Interrupt

[in, out] Specifies a pointer to an interrupt object. This value must be supplied by [**IoConnectInterrupt**](nf-wdm-ioconnectinterrupt.md) or [**IoConnectInterruptEx**](nf-wdm-ioconnectinterruptex.md).

## -returns

**KeAcquireInterruptSpinLock** returns the current IRQL at the time the routine is called. This value is passed to [**KeReleaseInterruptSpinLock**](nf-wdm-kereleaseinterruptspinlock.md) when the spin lock is released.

## -remarks

Drivers use the interrupt spin lock to synchronize access to memory shared with the interrupt's ISR. The driver can release the spin lock by calling [**KeReleaseInterruptSpinLock**](nf-wdm-kereleaseinterruptspinlock.md).

Any code that executes while the interrupt spin lock is held does so at IRQL = DIRQL for the specified *Interrupt*, so it must execute very quickly. For more information, see [Using Critical Sections](/windows-hardware/drivers/kernel/using-critical-sections).

The preferred way to synchronize a driver routine to an ISR is to use the [**KeSynchronizeExecution**](nf-wdm-kesynchronizeexecution.md) routine.

Starting with Windows 8, a driver can use [**IoConnectInterruptEx**](nf-wdm-ioconnectinterruptex.md) to register an interrupt service routine that runs at IRQL = PASSIVE\_LEVEL and that does not use a spin lock for interrupt synchronization. If *Interrupt* points to an interrupt object that connects to a passive-level ISR, **KeAcquireInterruptSpinLock** causes a bug check. For more information, see [Using Passive-Level Interrupt Service Routines](/windows-hardware/drivers/kernel/using-passive-level-interrupt-handling-routines).

Callers must be running at IRQL \<= DIRQL for *Interrupt*. (This is the value the driver passed as the *SynchronizeIrql* parameter of [**IoConnectInterrupt**](nf-wdm-ioconnectinterrupt.md) when *Interrupt* is created.)

## -see-also

[**IoConnectInterrupt**](nf-wdm-ioconnectinterrupt.md)

[**KeReleaseInterruptSpinLock**](nf-wdm-kereleaseinterruptspinlock.md)

[**KeSynchronizeExecution**](nf-wdm-kesynchronizeexecution.md)
