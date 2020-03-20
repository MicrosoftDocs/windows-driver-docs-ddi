---
UID: NS:parallel._PARALLEL_INTERRUPT_SERVICE_ROUTINE
title: _PARALLEL_INTERRUPT_SERVICE_ROUTINE (parallel.h)
description: The PARALLEL_INTERRUPT_SERVICE_ROUTINE structure specifies interrupt services that a kernel-mode driver can connect to the operation of a parallel port.
old-location: parports\parallel_interrupt_service_routine.htm
tech.root: parports
ms.assetid: dff10a68-f7c4-4f7a-a3f7-3697fc88992a
ms.date: 02/15/2018
keywords: ["_PARALLEL_INTERRUPT_SERVICE_ROUTINE structure"]
ms.keywords: "*PPARALLEL_INTERRUPT_SERVICE_ROUTINE, PARALLEL_INTERRUPT_SERVICE_ROUTINE, PARALLEL_INTERRUPT_SERVICE_ROUTINE structure [Parallel Ports], PPARALLEL_INTERRUPT_SERVICE_ROUTINE, PPARALLEL_INTERRUPT_SERVICE_ROUTINE structure pointer [Parallel Ports], _PARALLEL_INTERRUPT_SERVICE_ROUTINE, cisspd_db43e8c1-06d8-4a00-8f66-896987a45b83.xml, parallel/PARALLEL_INTERRUPT_SERVICE_ROUTINE, parallel/PPARALLEL_INTERRUPT_SERVICE_ROUTINE, parports.parallel_interrupt_service_routine"
f1_keywords:
 - "parallel/PARALLEL_INTERRUPT_SERVICE_ROUTINE"
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Windows
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
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- parallel.h
api_name:
- PARALLEL_INTERRUPT_SERVICE_ROUTINE
product:
- Windows
targetos: Windows
req.typenames: PARALLEL_INTERRUPT_SERVICE_ROUTINE, *PPARALLEL_INTERRUPT_SERVICE_ROUTINE
---

# _PARALLEL_INTERRUPT_SERVICE_ROUTINE structure


## -description


The PARALLEL_INTERRUPT_SERVICE_ROUTINE structure specifies interrupt services that a kernel-mode driver can connect to the operation of a parallel port.


## -syntax


```cpp
typedef struct _PARALLEL_INTERRUPT_SERVICE_ROUTINE {
  PKSERVICE_ROUTINE          InterruptServiceRoutine;
  PVOID                      InterruptServiceContext;
  PPARALLEL_DEFERRED_ROUTINE DeferredPortCheckRoutine;
  PVOID                      DeferredPortCheckContext;
} PARALLEL_INTERRUPT_SERVICE_ROUTINE, *PPARALLEL_INTERRUPT_SERVICE_ROUTINE;
```


## -struct-fields




### -field InterruptServiceRoutine

Pointer to an interrupt service routine.


### -field InterruptServiceContext

Pointer to a context for the interrupt service routine.


### -field DeferredPortCheckRoutine

Pointer to an optional deferred port check routine:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*DeferredPortCheckRoutine) (
    IN PVOID DeferredContext
);</pre>
</td>
</tr>
</table></span></div>
<b>Parameters</b>





#### DeferredContext

Pointer to a context for the deferred port check routine.


### -field DeferredPortCheckContext

Pointer to an optional context for the deferred port check routine.


## -remarks



A kernel-mode driver can connect a device-specific interrupt service routine and a deferred port check routine to the parallel port.

<div class="alert"><b>Note</b>    Microsoft does not recommend using a client-supplied interrupt routine. The use of interrupts might cause system instability. By default, the <a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a> request is disabled. For more information, see <a href="https://docs.microsoft.com/previous-versions/ff543934(v=vs.85)">Connecting an Interrupt Service Routine to a ParallelPort</a>.</div>
<div> </div>



## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_disconnect_interrupt.md">IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a>



<a href="..\parallel\ns-parallel-_parallel_interrupt_information.md">PARALLEL_INTERRUPT_INFORMATION</a>



 

 


