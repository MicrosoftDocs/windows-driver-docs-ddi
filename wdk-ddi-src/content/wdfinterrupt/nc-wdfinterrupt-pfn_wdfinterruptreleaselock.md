---
UID: NC:wdfinterrupt.PFN_WDFINTERRUPTRELEASELOCK
title: PFN_WDFINTERRUPTRELEASELOCK
author: windows-driver-content
description: The WdfInterruptReleaseLock method ends a code sequence that executes at the device's DIRQL while holding an interrupt object's spin lock.
old-location: wdf\wdfinterruptreleaselock.htm
tech.root: wdf
ms.assetid: a3b68f6f-d482-4350-a5b8-9fe6afdefb69
ms.date: 1/11/2018
ms.keywords: wdf.wdfinterruptreleaselock, PFN_WDFINTERRUPTRELEASELOCK, WdfInterruptReleaseLock callback function, WdfInterruptReleaseLock, wdfinterrupt/WdfInterruptReleaseLock, DFInterruptObjectRef_70637f8b-a7d9-4637-b02c-1ebed3e363c7.xml, kmdf.wdfinterruptreleaselock
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdfinterrupt.h
apiname:
-	WdfInterruptReleaseLock
product:
- Windows
targetos: Windows
req.typenames: WDF_COINSTALLER_INSTALL_OPTIONS, *PWDF_COINSTALLER_INSTALL_OPTIONS
req.product: Windows 10 or later.
---

# PFN_WDFINTERRUPTRELEASELOCK callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptReleaseLock</b> method ends a code sequence that executes at the device's DIRQL while holding an interrupt object's spin lock.

For passive level interrupt objects, the method ends a code sequence that executes at passive level while holding an interrupt object's passive lock.


## -prototype


```
VOID WdfInterruptReleaseLock(
  _In_ WDFINTERRUPT Interrupt
);
```


## -parameters




### -param DriverGlobals



### -param WDFINTERRUPT






#### - Interrupt [in]

A handle to a framework interrupt object.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


The <b>WdfInterruptReleaseLock</b> method releases the specified interrupt object's spin lock or wait lock and returns the processor's IRQL to the level that it was set to before the driver called <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>.

Your driver cannot call <b>WdfInterruptReleaseLock</b> before the framework has called the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a> callback function or after the framework has called the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a> callback function.

For more information about the <b>WdfInterruptReleaseLock</b> method, see <a href="https://msdn.microsoft.com/a24477dc-f75d-4ab6-8695-d8a85247e276">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.

This method must be called at the DIRQL that was set by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>.

For passive level interrupts, the driver must call <b>WdfInterruptReleaseLock</b> at IRQL = PASSIVE_LEVEL.



## -see-also

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsynchronize.md">WdfInterruptSynchronize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a>

 

 


