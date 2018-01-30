---
UID: NS:parallel._PARALLEL_INTERRUPT_SERVICE_ROUTINE
title: "_PARALLEL_INTERRUPT_SERVICE_ROUTINE"
author: windows-driver-content
description: The PARALLEL_INTERRUPT_SERVICE_ROUTINE structure specifies interrupt services that a kernel-mode driver can connect to the operation of a parallel port.
old-location: parports\parallel_interrupt_service_routine.htm
old-project: parports
ms.assetid: dff10a68-f7c4-4f7a-a3f7-3697fc88992a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PPARALLEL_INTERRUPT_SERVICE_ROUTINE, parallel/PARALLEL_INTERRUPT_SERVICE_ROUTINE, parallel/PPARALLEL_INTERRUPT_SERVICE_ROUTINE, PARALLEL_INTERRUPT_SERVICE_ROUTINE structure [Parallel Ports], PARALLEL_INTERRUPT_SERVICE_ROUTINE, _PARALLEL_INTERRUPT_SERVICE_ROUTINE, cisspd_db43e8c1-06d8-4a00-8f66-896987a45b83.xml, parports.parallel_interrupt_service_routine, *PPARALLEL_INTERRUPT_SERVICE_ROUTINE, PPARALLEL_INTERRUPT_SERVICE_ROUTINE structure pointer [Parallel Ports]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	parallel.h
apiname:
-	PARALLEL_INTERRUPT_SERVICE_ROUTINE
product: Windows
targetos: Windows
req.typenames: "*PPARALLEL_INTERRUPT_SERVICE_ROUTINE, PARALLEL_INTERRUPT_SERVICE_ROUTINE"
---

# _PARALLEL_INTERRUPT_SERVICE_ROUTINE structure


## -description


The PARALLEL_INTERRUPT_SERVICE_ROUTINE structure specifies interrupt services that a kernel-mode driver can connect to the operation of a parallel port.


## -syntax


````
typedef struct _PARALLEL_INTERRUPT_SERVICE_ROUTINE {
  PKSERVICE_ROUTINE          InterruptServiceRoutine;
  PVOID                      InterruptServiceContext;
  PPARALLEL_DEFERRED_ROUTINE DeferredPortCheckRoutine;
  PVOID                      DeferredPortCheckContext;
} PARALLEL_INTERRUPT_SERVICE_ROUTINE, *PPARALLEL_INTERRUPT_SERVICE_ROUTINE;
````


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
</table></span></div><b>Parameters</b>




#### DeferredContext

Pointer to a context for the deferred port check routine.


### -field DeferredPortCheckContext

Pointer to an optional context for the deferred port check routine.


## -remarks


A kernel-mode driver can connect a device-specific interrupt service routine and a deferred port check routine to the parallel port.
<div class="alert"><b>Note</b>    Microsoft does not recommend using a client-supplied interrupt routine. The use of interrupts might cause system instability. By default, the <a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a> request is disabled. For more information, see <a href="https://msdn.microsoft.com/62d3a388-6de6-4019-ab95-56b5e96d0891">Connecting an Interrupt Service Routine to a ParallelPort</a>.</div><div> </div>


## -see-also

<a href="..\parallel\ns-parallel-_parallel_interrupt_information.md">PARALLEL_INTERRUPT_INFORMATION</a>

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_disconnect_interrupt.md">IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT</a>

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PARALLEL_INTERRUPT_SERVICE_ROUTINE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

