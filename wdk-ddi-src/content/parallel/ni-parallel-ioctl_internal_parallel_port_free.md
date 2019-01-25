---
UID: NI:parallel.IOCTL_INTERNAL_PARALLEL_PORT_FREE
title: IOCTL_INTERNAL_PARALLEL_PORT_FREE (parallel.h)
description: The IOCTL_INTERNAL_PARALLEL_PORT_FREE request frees a parallel port.
old-location: parports\ioctl_internal_parallel_port_free.htm
tech.root: parports
ms.assetid: bdf44009-4898-4890-9441-918e1647566d
ms.date: 02/15/2018
ms.keywords: IOCTL_INTERNAL_PARALLEL_PORT_FREE, IOCTL_INTERNAL_PARALLEL_PORT_FREE control code [Parallel Ports], cisspd_ec1947dc-7124-445b-8b4a-759d6cba8225.xml, parallel/IOCTL_INTERNAL_PARALLEL_PORT_FREE, parports.ioctl_internal_parallel_port_free
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	parallel.h
api_name:
-	IOCTL_INTERNAL_PARALLEL_PORT_FREE
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_PARALLEL_PORT_FREE IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_PARALLEL_PORT_FREE</b> request frees a parallel port. After using a parallel port, a client must free it. Microsoft recommends using the system-supplied <a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE</a> callback to free a parallel port because there is no functional advantage to using an <b>IOCTL_INTERNAL_PARALLEL_PORT_FREE</b> request to free the port.

For more information, see <a href="https://msdn.microsoft.com/ea3a1998-9e31-4047-9193-6b402db222c9">Synchronizing the Use of a ParallelPort</a>.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports.


## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a>



<a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE</a>



 

 


