---
UID: NS:parallel._PARALLEL_INTERRUPT_INFORMATION
title: _PARALLEL_INTERRUPT_INFORMATION (parallel.h)
description: The PARALLEL_INTERRUPT_INFORMATION structure specifies information that a kernel-mode driver can use in the context of an ISR that the driver connects to a parallel port.
old-location: parports\parallel_interrupt_information.htm
tech.root: parports
ms.assetid: aa4baa12-c349-4961-9694-b8fb3cd8dc50
ms.date: 02/15/2018
keywords: ["PARALLEL_INTERRUPT_INFORMATION structure"]
ms.keywords: "*PPARALLEL_INTERRUPT_INFORMATION, PARALLEL_INTERRUPT_INFORMATION, PARALLEL_INTERRUPT_INFORMATION structure [Parallel Ports], PPARALLEL_INTERRUPT_INFORMATION, PPARALLEL_INTERRUPT_INFORMATION structure pointer [Parallel Ports], _PARALLEL_INTERRUPT_INFORMATION, cisspd_3912e608-5549-4b0a-a48d-fdc34af7bc04.xml, parallel/PARALLEL_INTERRUPT_INFORMATION, parallel/PPARALLEL_INTERRUPT_INFORMATION, parports.parallel_interrupt_information"
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
targetos: Windows
req.typenames: PARALLEL_INTERRUPT_INFORMATION, *PPARALLEL_INTERRUPT_INFORMATION
f1_keywords:
 - _PARALLEL_INTERRUPT_INFORMATION
 - parallel/_PARALLEL_INTERRUPT_INFORMATION
 - PPARALLEL_INTERRUPT_INFORMATION
 - parallel/PPARALLEL_INTERRUPT_INFORMATION
 - PARALLEL_INTERRUPT_INFORMATION
 - parallel/PARALLEL_INTERRUPT_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - parallel.h
api_name:
 - PARALLEL_INTERRUPT_INFORMATION
---

# _PARALLEL_INTERRUPT_INFORMATION structure


## -description

The PARALLEL_INTERRUPT_INFORMATION structure specifies information that a kernel-mode driver can use in the context of an ISR that the driver connects to a parallel port.

## -struct-fields

### -field InterruptObject

Pointer to the parallel port interrupt object.

### -field TryAllocatePortAtInterruptLevel

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE (ISR)</a> callback routine that a kernel-mode driver can use to attempt to allocate the parallel port at IRQL = DIRQL.

### -field FreePortFromInterruptLevel

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE (ISR)</a> callback routine that a kernel-mode driver can use to free the parallel port at IRQL = DIRQL.

### -field Context

Pointer to the device extension of a functional device object that represents the parallel port.

## -syntax

```cpp
typedef struct _PARALLEL_INTERRUPT_INFORMATION {
  PKINTERRUPT                    InterruptObject;
  PPARALLEL_TRY_ALLOCATE_ROUTINE TryAllocatePortAtInterruptLevel;
  PPARALLEL_FREE_ROUTINE         FreePortFromInterruptLevel;
  PVOID                          Context;
} PARALLEL_INTERRUPT_INFORMATION, *PPARALLEL_INTERRUPT_INFORMATION;
```

## -remarks

A kernel-mode driver can use the parallel interrupt information in the context of an interrupt service routine (ISR). A driver connects an ISR using an <a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a> request.

<div class="alert"><b>Note</b>    Microsoft does not recommend using a client-supplied interrupt routine. The use of interrupts might cause system instability. By default, the IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT request is disabled. For more information, see <a href="https://docs.microsoft.com/previous-versions/ff543934(v=vs.85)">Connecting an Interrupt Service Routine to a ParallelPort</a>.</div>
<div> </div>

## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_disconnect_interrupt.md">IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT</a>



<a href="..\parallel\ns-parallel-_parallel_interrupt_service_routine.md">PARALLEL_INTERRUPT_SERVICE_ROUTINE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a>



<a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE (ISR)</a>



<a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE (ISR)</a>

