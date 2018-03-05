---
UID: NC:parallel.PPARALLEL_TRY_ALLOCATE_ROUTINE
title: PPARALLEL_TRY_ALLOCATE_ROUTINE
author: windows-driver-content
description: The PPARALLEL_TRY_ALLOCATE_ROUTINE-typed (ISR) callback routine attempts to allocate a parallel port at IRQL = DIRQL. The system-supplied function driver for parallel ports supplies this routine.
old-location: parports\parallel_try_allocate_routine__isr_.htm
old-project: parports
ms.assetid: bc69e347-8ef7-4a80-9ef4-bbc03f5586c4
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PPARALLEL_TRY_ALLOCATE_ROUTINE, ParallelTryAllocateRoutine, ParallelTryAllocateRoutine callback function [Parallel Ports], cisspd_737cb583-bcc9-46e9-915b-e073da2c11bf.xml, parallel/ParallelTryAllocateRoutine, parports.parallel_try_allocate_routine__isr_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: parallel.h
req.include-header: Parallel.h
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
req.irql: DIRQL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	parallel.h
api_name:
-	ParallelTryAllocateRoutine
product: Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PPARALLEL_TRY_ALLOCATE_ROUTINE callback


## -description


The <i>PPARALLEL_TRY_ALLOCATE_ROUTINE</i>-typed (ISR) callback routine attempts to allocate a parallel port at IRQL = DIRQL. The system-supplied function driver for parallel ports supplies this routine.


## -prototype


````
typedef BOOLEAN ParallelTryAllocateRoutine(
  _In_ PVOID TryAllocateContext
);
````


## -parameters




### -param TryAllocateContext [in]

Pointer to the device extension of a functional device object that represents a parallel port.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>TRUE</b></dt>
</dl>
</td>
<td width="60%">
The parallel port was allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FALSE</b></dt>
</dl>
</td>
<td width="60%">
The parallel port was not allocated.

</td>
</tr>
</table>
 




## -remarks



A kernel-mode driver connects an interrupt service routine by using an <a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a>, which returns a <a href="..\parallel\ns-parallel-_parallel_interrupt_information.md">PARALLEL_INTERRUPT_INFORMATION</a> structure. This structure includes the <b>TryAllocatePortAtInterruptLevel</b> member, which is a pointer to the system-supplied <i>PPARALLEL_TRY_ALLOCATE_ROUTINE</i> (ISR) callback.

The <i>PPARALLEL_TRY_ALLOCATE_ROUTINE</i> (ISR) callback is nonblocking, does not queue an allocate request, and returns immediately.

A driver uses the <i>PPARALLEL_TRY_ALLOCATE_ROUTINE</i> (ISR) callback in conjunction with a driver-supplied ISR. If the driver does not have a parallel port allocated when the driver's ISR is called, the driver can use this callback.

For more information about allocating a parallel port in an ISR, see <a href="https://msdn.microsoft.com/62d3a388-6de6-4019-ab95-56b5e96d0891">Connecting an Interrupt Service Routine to a ParallelPort</a>.

<div class="alert"><b>Note</b>    The <i>PPARALLEL_TRY_ALLOCATE_ROUTINE</i> (ISR) callback is untested. Microsoft does not recommend using a client-supplied interrupt routine. The use of interrupts might cause system instability. By default, the <a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a> request is disabled.</div>
<div> </div>



## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_disconnect_interrupt.md">IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT</a>



<a href="..\parallel\ns-parallel-_parallel_interrupt_information.md">PARALLEL_INTERRUPT_INFORMATION</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_free.md">IOCTL_INTERNAL_PARALLEL_PORT_FREE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE (ISR)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PPARALLEL_TRY_ALLOCATE_ROUTINE callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

