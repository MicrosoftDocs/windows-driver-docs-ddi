---
UID: NC:wdfinterrupt.PFN_WDFINTERRUPTACQUIRELOCK
title: PFN_WDFINTERRUPTACQUIRELOCK
author: windows-driver-content
description: The WdfInterruptAcquireLock method begins a code sequence that executes at the device's device interrupt request level (DIRQL) while holding an interrupt object's spin lock.
old-location: wdf\wdfinterruptacquirelock.htm
tech.root: wdf
ms.assetid: 6a2fe0d5-bc7e-4d3e-8f47-8206fd42a36f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfinterruptacquirelock, PFN_WDFINTERRUPTACQUIRELOCK, WdfInterruptAcquireLock callback function, WdfInterruptAcquireLock, wdfinterrupt/WdfInterruptAcquireLock, DFInterruptObjectRef_9d3cd9a1-801c-437a-b1df-7e2819d1465a.xml, kmdf.wdfinterruptacquirelock
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<= DIRQL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdfinterrupt.h
apiname:
-	WdfInterruptAcquireLock
product:
- Windows
targetos: Windows
req.typenames: WDF_COINSTALLER_INSTALL_OPTIONS, *PWDF_COINSTALLER_INSTALL_OPTIONS
req.product: Windows 10 or later.
---

# PFN_WDFINTERRUPTACQUIRELOCK callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptAcquireLock</b> method begins a code sequence that executes at the device's device interrupt request level (DIRQL) while holding an interrupt object's spin lock.

For passive level interrupt objects, the method begins a code sequence that executes at passive level while holding an interrupt object's passive lock.




## -prototype


````
VOID WdfInterruptAcquireLock(
  _In_ WDFINTERRUPT Interrupt
);
````


## -parameters




### -param DriverGlobals



### -param WDFINTERRUPT






#### - Interrupt [in]

A handle to a framework interrupt object.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


When a driver calls <b>WdfInterruptAcquireLock</b> on a DIRQL interrupt object, the system raises the processor's IRQL to the device's DIRQL and acquires the spin lock that the driver specified in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure. As a result, the interrupt object's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> and <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a> callback functions (and any other code that calls <b>WdfInterruptAcquireLock</b> for the same interrupt object) cannot execute.

When the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>, the system returns the processor's IRQL to its previous level and releases the spin lock.

When a driver calls <b>WdfInterruptAcquireLock</b> on a passive-level interrupt object, the system acquires the passive-level interrupt lock that the driver configured in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure.

When the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>, the system releases the interrupt lock.

For passive level interrupts, the driver must call <b>WdfInterruptAcquireLock</b> at IRQL = PASSIVE_LEVEL.

Do not call <b>WdfInterruptAcquireLock</b> from an arbitrary thread context,  such as a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.

You can use <b>WdfInterruptAcquireLock</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a> if your driver must execute a few lines of code without being preempted and with servicing of device interrupts effectively disabled. For larger sections of code, your driver should provide an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a> callback function.

Your driver cannot call <b>WdfInterruptAcquireLock</b> before the framework has called the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a> callback function or after the framework has called the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a> callback function.

After your driver calls <b>WdfInterruptAcquireLock</b>, it must not call the method again for the same interrupt object before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>.

For more information about the <b>WdfInterruptAcquireLock</b> method, see <a href="https://msdn.microsoft.com/a24477dc-f75d-4ab6-8695-d8a85247e276">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.

For passive-level interrupt objects, drivers must call <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterrupttrytoacquirelock.md">WdfInterruptTryToAcquireLock</a> instead of <b>WdfInterruptAcquireLock</b>, when running in an arbitrary thread, such as a <a href="https://msdn.microsoft.com/5C311AF5-A67A-4F97-8605-1DD16C9D7839">queue object callback function</a>. For example, the driver might call <b>WdfInterruptTryToAcquireLock</b> from <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a>.

Doing so avoids the possibility of deadlock, as described in the following scenario.
<ol>
<li>In order to determine if its device interrupted, the function driver for an SPB peripheral device sends I/O to its bus from within its ISR, with the passive-level interrupt lock held.</li>
<li>  The bus driver completes a second request in the same thread in which it received the above request.</li>
<li>The completion routine of the second request sends a request to the peripheral driver.</li>
<li>  The peripheral driver's I/O dispatch routine calls <b>WdfInterruptAcquireLock</b>, which then deadlocks attempting to acquire the interrupt object's passive lock.</li>
</ol>


## -see-also

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsynchronize.md">WdfInterruptSynchronize</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a>

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterrupttrytoacquirelock.md">WdfInterruptTryToAcquireLock</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a>

<a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>

 

 


