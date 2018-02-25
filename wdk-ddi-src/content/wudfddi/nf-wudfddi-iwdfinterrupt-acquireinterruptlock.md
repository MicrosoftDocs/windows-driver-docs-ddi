---
UID: NF:wudfddi.IWDFInterrupt.AcquireInterruptLock
title: IWDFInterrupt::AcquireInterruptLock method
author: windows-driver-content
description: The AcquireInterruptLock method begins a code sequence that executes while holding an interrupt object's lock.
old-location: wdf\iwdfinterrupt_acquireinterruptlock.htm
old-project: wdf
ms.assetid: 2ED55AEC-2446-4E66-AAFD-A22BAB3FC9C7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, A, AcquireInterruptLock method, AcquireInterruptLock method, IWDFInterrupt interface, AcquireInterruptLock,IWDFInterrupt.AcquireInterruptLock, D, F, I, IWDFInterrupt, IWDFInterrupt interface, AcquireInterruptLock method, IWDFInterrupt::AcquireInterruptLock, L, W, c, e, i, k, n, o, p, q, r, t, u, umdf.iwdfinterrupt_acquireinterruptlock, wdf.iwdfinterrupt_acquireinterruptlock, wudfddi/IWDFInterrupt::AcquireInterruptLock"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFInterrupt.AcquireInterruptLock
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFInterrupt::AcquireInterruptLock method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AcquireInterruptLock</b> method begins a code sequence that executes while holding an interrupt object's lock.


## -syntax


````
void AcquireInterruptLock();
````


## -parameters






## -returns



This method does not return a value.




## -remarks



When a driver calls <b>AcquireInterruptLock</b>, the system acquires the framework's interrupt lock.

When the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh451319">ReleaseInterruptLock</a>, the system releases the interrupt lock.

You can use <b>AcquireInterruptLock</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451319">ReleaseInterruptLock</a> if your driver must execute a few lines of code without being preempted and with interrupt servicing disabled.



Your driver cannot call <b>AcquireInterruptLock</b> before the framework has called the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_enable.md">OnInterruptEnable</a> callback function or after the framework has called the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_disable.md">OnInterruptDisable</a> callback function.

After your driver calls <b>AcquireInterruptLock</b>, it must not call the method again for the same interrupt object before calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451319">ReleaseInterruptLock</a>.



When running in an arbitrary thread, such as an I/O queue callback method, drivers must call <a href="https://msdn.microsoft.com/4A109CDF-C5DE-4BAE-AA4E-294EA5CE86C5">IWDFInterrupt::TryToAcquireInterruptLock</a> instead of <b>IWDFInterrupt::AcquireInterruptLock</b>. For example, the driver calls <b>IWDFInterrupt::TryToAcquireInterruptLock</b> from <a href="https://msdn.microsoft.com/library/windows/hardware/ff556875">IQueueCallbackRead::OnRead</a>.

Doing so avoids the possibility of deadlock, as described in the following scenario.

<ol>
<li>In order to determine if its device interrupted, a UMDF sends I/O to its bus from within its ISR, with the interrupt lock held.</li>
<li>  The bus driver completes a second request in the same thread in which it received the above request.</li>
<li>The completion routine of the second request sends a request to the UMDF driver.</li>
<li>  The UMDF driver's I/O dispatch routine calls <b>IWDFInterrupt::AcquireInterruptLock</b>, which then deadlocks attempting to acquire the interrupt lock.</li>
</ol>
The driver must not attempt to acquire the lock recursively. If connected to the debugger, the framework introduces a breakpoint in this scenario.

For more information about manual interrupt locking, see <a href="https://msdn.microsoft.com/a24477dc-f75d-4ab6-8695-d8a85247e276">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>



<a href="https://msdn.microsoft.com/55ED21D9-D704-4E38-AFCF-B1D1FDB67DB3">IWDFInterrupt::ReleaseInterruptLock</a>



<a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFInterrupt::AcquireInterruptLock method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

