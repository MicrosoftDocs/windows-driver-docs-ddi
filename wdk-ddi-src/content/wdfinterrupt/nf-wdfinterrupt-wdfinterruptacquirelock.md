---
UID: NF:wdfinterrupt.WdfInterruptAcquireLock
title: WdfInterruptAcquireLock function (wdfinterrupt.h)
description: The WdfInterruptAcquireLock method begins a code sequence that executes at the device's device interrupt request level (DIRQL) while holding an interrupt object's spin lock.
old-location: wdf/wdfinterruptacquirelock.htm
tech.root: wdf
ms.date: 08/11/2022
keywords: ["PFN_WDFINTERRUPTACQUIRELOCK callback"]
ms.keywords: wdf.wdfinterruptacquirelock, PFN_WDFINTERRUPTACQUIRELOCK, WdfInterruptAcquireLock callback function, WdfInterruptAcquireLock, wdfinterrupt/WdfInterruptAcquireLock, DFInterruptObjectRef_9d3cd9a1-801c-437a-b1df-7e2819d1465a.xml, kmdf.wdfinterruptacquirelock
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, WdfInterruptLock, WdfInterruptLockRelease
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DIRQL
targetos: Windows
req.typenames: WDF_COINSTALLER_INSTALL_OPTIONS, *PWDF_COINSTALLER_INSTALL_OPTIONS
f1_keywords:
 - PFN_WDFINTERRUPTACQUIRELOCK
 - wdfinterrupt/PFN_WDFINTERRUPTACQUIRELOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdfinterrupt.h
api_name:
 - PFN_WDFINTERRUPTACQUIRELOCK
---

# PFN_WDFINTERRUPTACQUIRELOCK function

## -description

**[Applies to KMDF and UMDF]**

The **WdfInterruptAcquireLock** method begins a code sequence that executes at the device's device interrupt request level (DIRQL) while holding an interrupt object's spin lock.

For passive level interrupt objects, the method begins a code sequence that executes at passive level while holding an interrupt object's passive lock.

## -parameters

### -param DriverGlobals

### -param Interrupt [in]

A handle to a framework interrupt object.

## -prototype

```cpp
VOID
(*PFN_WDFINTERRUPTACQUIRELOCK)(
    IN PWDF_DRIVER_GLOBALS DriverGlobals,
    WDFINTERRUPT Interrupt
    );
```

## -returns

## -remarks

A bug check occurs if the driver supplies an invalid object handle.

When a driver calls **WdfInterruptAcquireLock** on a DIRQL interrupt object, the system raises the processor's IRQL to the device's DIRQL and acquires the spin lock that the driver specified in the interrupt object's [WDF_INTERRUPT_CONFIG](../wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config.md) structure. As a result, the interrupt object's [EvtInterruptIsr](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr.md) and [EvtInterruptSynchronize](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md) callback functions (and any other code that calls **WdfInterruptAcquireLock** for the same interrupt object) cannot execute.

When the driver calls [WdfInterruptReleaseLock](/previous-versions/ff547376(v=vs.85)), the system returns the processor's IRQL to its previous level and releases the spin lock.

When a driver calls **WdfInterruptAcquireLock** on a passive-level interrupt object, the system acquires the passive-level interrupt lock that the driver configured in the interrupt object's [WDF_INTERRUPT_CONFIG](../wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config.md) structure.

When the driver calls [WdfInterruptReleaseLock](/previous-versions/ff547376(v=vs.85)), the system releases the interrupt lock.

For passive level interrupts, the driver must call **WdfInterruptAcquireLock** at IRQL = PASSIVE_LEVEL.

Do not call **WdfInterruptAcquireLock** from an arbitrary thread context,  such as a [request handler](/windows-hardware/drivers/wdf/request-handlers).

You can use **WdfInterruptAcquireLock** and [WdfInterruptReleaseLock](/previous-versions/ff547376(v=vs.85)) if your driver must execute a few lines of code without being preempted and with servicing of device interrupts effectively disabled. For larger sections of code, your driver should provide an [EvtInterruptSynchronize](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md) callback function.

Your driver cannot call **WdfInterruptAcquireLock** before the framework has called the driver's [EvtInterruptEnable](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable.md) callback function or after the framework has called the driver's [EvtInterruptDisable](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable.md) callback function.

After your driver calls **WdfInterruptAcquireLock**, it must not call the method again for the same interrupt object before calling [WdfInterruptReleaseLock](/previous-versions/ff547376(v=vs.85)).

For more information about the **WdfInterruptAcquireLock** method, see [Synchronizing Interrupt Code](/windows-hardware/drivers/wdf/synchronizing-interrupt-code).

For more information about handling interrupts in framework-based drivers, see [Handling Hardware Interrupts](/windows-hardware/drivers/wdf/handling-hardware-interrupts).

For passive-level interrupt objects, drivers must call [WdfInterruptTryToAcquireLock](../wdfinterrupt/nf-wdfinterrupt-wdfinterrupttrytoacquirelock.md) instead of **WdfInterruptAcquireLock**, when running in an arbitrary thread, such as a [queue object callback function](../wdfio/index.md). For example, the driver might call **WdfInterruptTryToAcquireLock** from [EvtIoRead](../wdfio/nc-wdfio-evt_wdf_io_queue_io_read.md).

Doing so avoids the possibility of deadlock, as described in the following scenario.

1. In order to determine if its device interrupted, the function driver for an SPB peripheral device sends I/O to its bus from within its ISR, with the passive-level interrupt lock held.
1. The bus driver completes a second request in the same thread in which it received the above request.
1. The completion routine of the second request sends a request to the peripheral driver.
1. The peripheral driver's I/O dispatch routine calls **WdfInterruptAcquireLock**, which then deadlocks attempting to acquire the interrupt object's passive lock.

## -see-also

- [WdfInterruptSynchronize](../wdfinterrupt/nf-wdfinterrupt-wdfinterruptsynchronize.md)
- [EvtInterruptSynchronize](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md)
- [EvtInterruptDisable](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable.md)
- [WdfInterruptTryToAcquireLock](../wdfinterrupt/nf-wdfinterrupt-wdfinterrupttrytoacquirelock.md)
- [EvtInterruptEnable](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable.md)
- [WDF_INTERRUPT_CONFIG](../wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config.md)
- [EvtInterruptIsr](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr.md)
- [WdfInterruptReleaseLock](/previous-versions/ff547376(v=vs.85))