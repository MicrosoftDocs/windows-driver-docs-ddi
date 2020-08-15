---
UID: NC:parallel.PPARALLEL_FREE_ROUTINE
title: PPARALLEL_FREE_ROUTINE (parallel.h)
description: The PPARALLEL_FREE_ROUTINE-typed callback routine frees a parallel port. The system-supplied function driver for parallel ports supplies this routine.
old-location: parports\pparallel_free_routine.htm
tech.root: parports
ms.assetid: 730872ee-3dfd-48c7-a86e-1a420e59471f
ms.date: 02/15/2018
keywords: ["PPARALLEL_FREE_ROUTINE callback"]
ms.keywords: "(*PPARALLEL_FREE_ROUTINE), (*PPARALLEL_FREE_ROUTINE) callback function [Parallel Ports], cisspd_5f5bcbed-0df6-4b2a-ab88-a26f48976ad7.xml, parallel/(*PPARALLEL_FREE_ROUTINE), parports.pparallel_free_routine"
f1_keywords:
 - "parallel/(*PPARALLEL_FREE_ROUTINE)"
 - "(*PPARALLEL_FREE_ROUTINE)"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- parallel.h
api_name:
- (*PPARALLEL_FREE_ROUTINE)
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PPARALLEL_FREE_ROUTINE callback


## -description


The <i>PPARALLEL_FREE_ROUTINE</i>-typed callback routine frees a parallel port. The system-supplied function driver for parallel ports supplies this routine.


## -prototype


```cpp
typedef VOID (*PPARALLEL_FREE_ROUTINE)(
  _In_ PVOID FreeContext
);
```


## -parameters




### -param FreeContext 
[in]
Pointer to the device extension of a parallel port's functional device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">FDO</a>).


## -remarks



To obtain a pointer to the system-supplied <i>PPARALLEL_FREE_ROUTINE</i> callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a> request, which returns a <a href="..\parallel\ns-parallel-_parallel_port_information.md">PARALLEL_PORT_INFORMATION</a> structure. The <b>FreePort</b> member of the PARALLEL_PORT_INFORMATION structure is a pointer to this callback.

The driver should allocate a parallel port before freeing it. A driver can use <a href="..\parallel\nc-parallel-pparallel_query_waiters_routine.md">PPARALLEL_QUERY_WAITERS_ROUTINE</a> to determine the number of clients that are waiting to allocate the parallel port, and <a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE</a> to try to allocate the parallel port.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544809(v=vs.85)">Synchronizing the Use of a ParallelPort</a>.




## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ns-parallel-_parallel_port_information.md">PARALLEL_PORT_INFORMATION</a>



<a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE</a>



<a href="..\parallel\nc-parallel-pparallel_query_waiters_routine.md">PPARALLEL_QUERY_WAITERS_ROUTINE</a>



 

 


