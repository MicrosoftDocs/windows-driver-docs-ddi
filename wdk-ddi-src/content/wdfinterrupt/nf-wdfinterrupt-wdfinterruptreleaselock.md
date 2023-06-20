---
UID: NF:wdfinterrupt.WdfInterruptReleaseLock
title: WdfInterruptReleaseLock function (wdfinterrupt.h)
description: The WdfInterruptReleaseLock method ends a code sequence that executes at the device's DIRQL while holding an interrupt object's spin lock.
old-location: wdf/wdfinterruptreleaselock.htm
tech.root: wdf
ms.date: 08/11/2022
keywords: ["PFN_WDFINTERRUPTRELEASELOCK callback"]
ms.keywords: wdf.wdfinterruptreleaselock, PFN_WDFINTERRUPTRELEASELOCK, WdfInterruptReleaseLock callback function, WdfInterruptReleaseLock, wdfinterrupt/WdfInterruptReleaseLock, DFInterruptObjectRef_70637f8b-a7d9-4637-b02c-1ebed3e363c7.xml, kmdf.wdfinterruptreleaselock
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
req.irql: See Remarks section.
targetos: Windows
req.typenames: WDF_COINSTALLER_INSTALL_OPTIONS, *PWDF_COINSTALLER_INSTALL_OPTIONS
req.product: Windows 10 or later.
f1_keywords:
 - PFN_WDFINTERRUPTRELEASELOCK
 - wdfinterrupt/PFN_WDFINTERRUPTRELEASELOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdfinterrupt.h
api_name:
 - PFN_WDFINTERRUPTRELEASELOCK
---

# PFN_WDFINTERRUPTRELEASELOCK function

## -description

**[Applies to KMDF and UMDF]**

The **WdfInterruptReleaseLock** method ends a code sequence that executes at the device's DIRQL while holding an interrupt object's spin lock.

For passive level interrupt objects, the method ends a code sequence that executes at passive level while holding an interrupt object's passive lock.

## -parameters

### -param DriverGlobals

### -param Interrupt [in]

A handle to a framework interrupt object.

## -prototype

```cpp
VOID
(*PFN_WDFINTERRUPTRELEASELOCK)(
    IN PWDF_DRIVER_GLOBALS DriverGlobals,
    WDFINTERRUPT Interrupt
    );
```

## -returns

## -remarks

A bug check occurs if the driver supplies an invalid object handle.

The **WdfInterruptReleaseLock** method releases the specified interrupt object's spin lock or wait lock and returns the processor's IRQL to the level that it was set to before the driver called [WdfInterruptAcquireLock](/previous-versions/ff547340(v=vs.85)).

Your driver cannot call **WdfInterruptReleaseLock** before the framework has called the driver's [EvtInterruptEnable](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable.md) callback function or after the framework has called the driver's [EvtInterruptDisable](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable.md) callback function.

For more information about the **WdfInterruptReleaseLock** method, see [Synchronizing Interrupt Code](/windows-hardware/drivers/wdf/synchronizing-interrupt-code).

For more information about handling interrupts in framework-based drivers, see [Handling Hardware Interrupts](/windows-hardware/drivers/wdf/handling-hardware-interrupts).

This method must be called at the DIRQL that was set by [WdfInterruptAcquireLock](/previous-versions/ff547340(v=vs.85)).

For passive level interrupts, the driver must call **WdfInterruptReleaseLock** at IRQL = PASSIVE_LEVEL.

## -see-also

- [WdfInterruptSynchronize](../wdfinterrupt/nf-wdfinterrupt-wdfinterruptsynchronize.md)
- [WdfInterruptAcquireLock](/previous-versions/ff547340(v=vs.85))
- [EvtInterruptEnable](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable.md)
- [EvtInterruptDisable](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable.md)
