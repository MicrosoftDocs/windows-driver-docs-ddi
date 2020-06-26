---
UID: NC:wdm.KDEFERRED_ROUTINE
title: KDEFERRED_ROUTINE (wdm.h)
description: The callback routine performs actions, after an InterruptService returns, of a threaded DPC, The CustomDpc routine finishes the servicing of an I/O operation, after an InterruptService routine returns.The CustomThreadedDpc routine performs the action of a threaded DPC. The system executes this routine when the threaded DPC runs.The CustomTimerDpc routine executes after a timer object's time interval expires.
old-location: kernel\customdpc.htm
tech.root: kernel
ms.assetid: 4b94690a-cac9-4e36-ac51-34b02b4be28a
ms.date: 04/30/2018
keywords: ["KDEFERRED_ROUTINE callback function"]
ms.keywords: CustomDpc, CustomThreadedDpc, CustomTimerDpc, DrvrRtns_977bffb4-a7ff-4b2b-80c6-181d00462d69.xml, KDEFERRED_ROUTINE, MyDpc, MyDpc routine [Kernel-Mode Driver Architecture], kernel.customdpc, wdm/MyDpc
f1_keywords:
 - "wdm/MyDpc"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at DISPATCH_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- MyDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# KDEFERRED_ROUTINE callback function


## -description


The callback routine performs actions, after an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a> returns,  of a threaded DPC, 

The <i>CustomDpc</i> routine finishes the servicing of an I/O operation, after an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a> routine returns.

The <i>CustomThreadedDpc</i> routine performs the action of a threaded DPC. The system executes this routine when the threaded DPC runs.

The <i>CustomTimerDpc</i> routine executes after a timer object's time interval expires.


## -parameters




### -param Dpc [in]

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure, which represents the DPC object that is associated with this callback  routine.


### -param DeferredContext [in, optional]

For <i>CustomDpc</i>, a caller-supplied pointer to driver-defined context information that was specified in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>.

For <i>CustomThreadedDpc</i>, specifies driver-defined context information. When it initialized the DPC object, the driver supplied this value as the <i>DeferredContext</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializethreadeddpc">KeInitializeThreadedDpc</a>.

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure, which represents the DPC object associated with this <i>CustomTimerDpc</i> routine.


### -param SystemArgument1 [in, optional]

Caller-supplied pointer to driver-supplied information that was specified in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a>. When it added the DPC to the DPC queue, the driver supplied this value as the <i>SystemArgument1</i> parameter to <b>KeInsertQueueDpc</b>.

For <i>CustomTimerDpc</i>,  this value is not used.


### -param SystemArgument2 [in, optional]

Specifies driver-defined context information. When it added the DPC to the DPC queue, the driver supplied this value as the <i>SystemArgument2</i> parameter to <b>KeInsertQueueDpc</b>.

For <i>CustomTimerDpc</i>,  this value is not used.


## -remarks



<b>About implementing <i>CustomDpc</i>:  </b>To create a DPC object and register a <i>CustomDpc</i> routine for that object, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>. (If you need only one DPC routine, you can use a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_dpc_routine">DpcForIsr</a> routine and the system-allocated DPC object.)

To queue a <i>CustomDpc</i> routine for execution, a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a> routine must call <b>KeInsertQueueDpc</b>.

One or more <i>CustomDpc</i> routines can be used instead of, or in conjunction with, a <i>DpcForIsr</i> routine. A driver that maintains several internal IRP queues typically supplies a <i>CustomDpc</i> routine for each queue. Each <i>CustomDpc</i> routine is typically responsible for at least the following tasks:

<ul>
<li>
Completing the I/O operation that is described by the current IRP.

</li>
<li>
Dequeuing the next IRP from one of the driver's IRP queues. (Drivers that use the system-supplied IRP queue together with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_startio">StartIo</a> routine call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostartnextpacket">IoStartNextPacket</a>.)

</li>
<li>
Setting the I/O status block in the current IRP and calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a> for the completed request.

</li>
</ul>
A <i>CustomDpc</i> routine might also retry a failed operation or set up the next transfer for a large I/O request that has been broken into smaller pieces.

For more information about <i>CustomDpc</i> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/dpc-objects-and-dpcs">DPC Objects and DPCs</a>.



<b>About implementing <i>CustomThreadedDpc</i>:  </b>A driver registers a <i>CustomThreadedDpc</i> for a DPC object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializethreadeddpc">KeInitializeThreadedDpc</a>. To actually add the DPC to the DPC queue so that the <i>CustomThreadedDpc</i> routine will be executed, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a>.

For more information about using <i>CustomThreadedDpc</i> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/threaded-dpcs">Threaded DPCs</a>.

A <i>CustomThreadedDpc</i> routine can run at IRQL = DISPATCH_LEVEL, or it can run at IRQL = PASSIVE_LEVEL in a real-time thread.



<b>About implementing <i>CustomTimerDpc</i>:  </b>To create a DPC object and register a <i>CustomTimerDpc</i> routine for that object, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>.

To queue a <i>CustomTimerDpc</i> routine for execution, a driver routine must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimer">KeSetTimer</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a>, supplying a DPC object pointer returned by <b>KeInitializeDpc</b>. The system calls the <i>CustomTimerDpc</i> routine when the timer interval expires.

For more information about <i>CustomTimerDpc</i> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/timer-objects-and-dpcs">Timer Objects and DPCs</a>.




#### Examples

To define a callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CustomDpc</i> callback routine that is named <code>MyCustomDpc</code>, use the KDEFERRED_ROUTINE type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>KDEFERRED_ROUTINE MyCustomDpc;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyCustomDpc(
    struct _KDPC  *Dpc,
    PVOID  DeferredContext,
    PVOID  SystemArgument1,
    PVOID  SystemArgument2
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>



## -see-also




<b>KeInitializeDpc</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimer">KeSetTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a>
 

 

