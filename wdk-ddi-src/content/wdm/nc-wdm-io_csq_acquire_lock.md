---
UID: NC:wdm.IO_CSQ_ACQUIRE_LOCK
title: IO_CSQ_ACQUIRE_LOCK (wdm.h)
description: The CsqAcquireLock routine is used by the system to acquire the lock for a driver-implemented, cancel-safe IRP queue.
old-location: kernel\csqacquirelock.htm
tech.root: kernel
ms.assetid: 8981e2f9-b456-48de-b31c-25a6884bcf12
ms.date: 04/30/2018
ms.keywords: CsqAcquireLock, CsqAcquireLock routine [Kernel-Mode Driver Architecture], DrvrRtns_02339dc6-f9f2-47b0-a0c9-df36f862b5d6.xml, IO_CSQ_ACQUIRE_LOCK, kernel.csqacquirelock, wdm/CsqAcquireLock
ms.topic: callback
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	CsqAcquireLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# IO_CSQ_ACQUIRE_LOCK callback function


## -description


The <i>CsqAcquireLock</i> routine is used by the system to acquire the lock for a driver-implemented, cancel-safe IRP queue.


## -parameters




### -param Csq [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the cancel-safe IRP queue.


### -param Irql [out]

Pointer to a variable that the <i>CsqAcquireLock</i> routine can use to store the current IRQL. The system passes the stored value <a href="https://msdn.microsoft.com/library/windows/hardware/ff542965">CsqReleaseLock</a> when it releases the lock.


## -returns



None




## -remarks



The driver specifies the <i>CsqAcquireLock</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqAcquireLock</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff549054">IoCsqInitialize</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549060">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

The system calls this routine to acquire a lock on the driver's IRP queue before attempting to insert or remove an IRP from the queue. The system calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542965">CsqReleaseLock</a> routine to release the lock.

If the driver uses a spin lock to implement locking for the queue, it must store the current IRQL for when it releases the spin lock. The system passes a pointer to an IRQL variable that the driver can use to store the current IRQL. The system passes the stored value as the <i>Irql</i> parameter to <i>CsqReleaseLock</i> when it releases the lock. Otherwise the driver can ignore the <i>Irql</i> parameter. For information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.

Drivers can use any locking mechanism to lock the queue, such as mutexes. For more information about mutexes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556417">Mutex Objects</a>.


#### Examples

To define a <i>CsqAcquireLock</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CsqAcquireLock</i> callback routine that is named <code>MyCsqAcquireLock</code>, use the IO_CSQ_ACQUIRE_LOCK type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_CSQ_ACQUIRE_LOCK MyCsqAcquireLock;</pre>
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
 MyCsqAcquireLock(
    PIO_CSQ  Csq,
    PKIRQL  Irql
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The IO_CSQ_ACQUIRE_LOCK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_CSQ_ACQUIRE_LOCK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542940">CsqCompleteCanceledIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542947">CsqInsertIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542956">CsqInsertIrpEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542959">CsqPeekNextIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542965">CsqReleaseLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542968">CsqRemoveIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549054">IoCsqInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549060">IoCsqInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549066">IoCsqInsertIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549067">IoCsqInsertIrpEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549070">IoCsqRemoveIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549072">IoCsqRemoveNextIrp</a>
 

 

