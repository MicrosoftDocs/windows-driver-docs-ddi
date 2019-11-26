---
UID: NF:wudfddi.IWDFInterrupt.TryToAcquireInterruptLock
title: IWDFInterrupt::TryToAcquireInterruptLock (wudfddi.h)
description: The TryToAcquireInterruptLock method acquires the interrupt lock if no other thread has already acquired it.
old-location: wdf\iwdfinterrupt_trytoacquireinterruptlock.htm
tech.root: wdf
ms.assetid: 4A109CDF-C5DE-4BAE-AA4E-294EA5CE86C5
ms.date: 02/26/2018
ms.keywords: IWDFInterrupt interface,TryToAcquireInterruptLock method, IWDFInterrupt.TryToAcquireInterruptLock, IWDFInterrupt::TryToAcquireInterruptLock, TryToAcquireInterruptLock, TryToAcquireInterruptLock method, TryToAcquireInterruptLock method,IWDFInterrupt interface, umdf.iwdfinterrupt_trytoacquireinterruptlock, wdf.iwdfinterrupt_trytoacquireinterruptlock, wudfddi/IWDFInterrupt::TryToAcquireInterruptLock
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFInterrupt.TryToAcquireInterruptLock"
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFInterrupt.TryToAcquireInterruptLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFInterrupt::TryToAcquireInterruptLock


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>TryToAcquireInterruptLock</b> method acquires the interrupt lock if no other thread has already acquired it.


## -returns



The method returns TRUE if the interrupt lock was successfully acquired. Otherwise, the method returns FALSE.




## -remarks



Unlike <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-acquireinterruptlock">IWDFInterrupt::AcquireInterruptLock</a>, <b>IWDFInterrupt::TryToAcquireInterruptLock</b> does not wait for the interrupt lock to become available if another thread is holding it.

When running in an arbitrary thread, such as an I/O queue callback method, drivers must call <b>IWDFInterrupt::TryToAcquireInterruptLock</b> instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-acquireinterruptlock">IWDFInterrupt::AcquireInterruptLock</a>. For example, the driver calls <b>IWDFInterrupt::TryToAcquireInterruptLock</b> from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackread-onread">IQueueCallbackRead::OnRead</a>. Doing so avoids the possibility of deadlock, as described in the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-acquireinterruptlock">IWDFInterrupt::AcquireInterruptLock</a>.

The driver must not attempt to acquire the lock recursively. If connected to the debugger, the framework introduces a breakpoint in this scenario.

For more information about manual interrupt locking, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronizing-interrupt-code">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in UMDF drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts">Accessing Hardware and Handling Interrupts</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfinterrupt">IWDFInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-acquireinterruptlock">IWDFInterrupt::AcquireInterruptLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439284">WdfInterruptTryToAcquireLock</a>
 

 

