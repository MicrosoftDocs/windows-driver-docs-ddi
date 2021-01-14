---
UID: NS:parallel._PARALLEL_PORT_INFORMATION
title: _PARALLEL_PORT_INFORMATION (parallel.h)
description: The PARALLEL_PORT_INFORMATION structure specifies information about the resources assigned to a parallel port, the capabilities of the parallel port, and pointers to callback routines that a kernel-mode driver can use to operate the parallel port.
old-location: parports\parallel_port_information.htm
tech.root: parports
ms.date: 02/15/2018
keywords: ["PARALLEL_PORT_INFORMATION structure"]
ms.keywords: "*PPARALLEL_PORT_INFORMATION, PARALLEL_PORT_INFORMATION, PARALLEL_PORT_INFORMATION structure [Parallel Ports], PPARALLEL_PORT_INFORMATION, PPARALLEL_PORT_INFORMATION structure pointer [Parallel Ports], _PARALLEL_PORT_INFORMATION, cisspd_ca857237-0c57-46e9-aedf-f6d40a25dbf8.xml, parallel/PARALLEL_PORT_INFORMATION, parallel/PPARALLEL_PORT_INFORMATION, parports.parallel_port_information"
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
req.typenames: PARALLEL_PORT_INFORMATION, *PPARALLEL_PORT_INFORMATION
f1_keywords:
 - _PARALLEL_PORT_INFORMATION
 - parallel/_PARALLEL_PORT_INFORMATION
 - PPARALLEL_PORT_INFORMATION
 - parallel/PPARALLEL_PORT_INFORMATION
 - PARALLEL_PORT_INFORMATION
 - parallel/PARALLEL_PORT_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - parallel.h
api_name:
 - _PARALLEL_PORT_INFORMATION
 - PPARALLEL_PORT_INFORMATION
 - PARALLEL_PORT_INFORMATION
---

# _PARALLEL_PORT_INFORMATION structure


## -description

The PARALLEL_PORT_INFORMATION structure specifies information about the resources assigned to a parallel port, the capabilities of the parallel port, and pointers to callback routines that a kernel-mode driver can use to operate the parallel port.

## -struct-fields

### -field OriginalController

Specifies the bus relative base I/O address of the parallel port registers.

### -field Controller

Pointer to the system-mapped base I/O location of the parallel port registers.

### -field SpanOfController

Specifies the size, in bytes, of the I/O space, allocated to the parallel port.

### -field TryAllocatePort

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE</a> callback that a kernel-mode driver can use to attempt to allocate the parallel port.

### -field FreePort

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE</a> callback that a kernel-mode driver can use to free the parallel port.

### -field QueryNumWaiters

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_query_waiters_routine.md">PPARALLEL_QUERY_WAITERS_ROUTINE</a> callback that a kernel-mode driver can use to determine the number of requests on the work queue of the parallel port.

### -field Context

Pointer to the device extension of parallel port.

## -syntax

```cpp
typedef struct _PARALLEL_PORT_INFORMATION {
  PHYSICAL_ADDRESS                OriginalController;
  PUCHAR                          Controller;
  ULONG                           SpanOfController;
  PPARALLEL_TRY_ALLOCATE_ROUTINE  TryAllocatePort;
  PPARALLEL_FREE_ROUTINE          FreePort;
  PPARALLEL_QUERY_WAITERS_ROUTINE QueryNumWaiters;
  PVOID                           Context;
} PARALLEL_PORT_INFORMATION, *PPARALLEL_PORT_INFORMATION;
```

## -remarks

An <a href="/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> request from the Plug and Play manager passes a translated resource list that contains the port information in a PARALLEL_PORT_INFORMATION structure. The system-supplied function driver for parallel ports saves the information in the extension of the parallel port and returns the information in response to an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a> request.

For more information, see <a href="/previous-versions/ff544223(v=vs.85)">Obtaining Information About a ParallelPort</a>.

## -see-also

<a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE</a>



<a href="/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_more_parallel_port_info.md">IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a>



<a href="..\parallel\ns-parallel-_more_parallel_port_information.md">MORE_PARALLEL_PORT_INFORMATION</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md">IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</a>



<a href="..\parallel\nc-parallel-pparallel_query_waiters_routine.md">PPARALLEL_QUERY_WAITERS_ROUTINE</a>

