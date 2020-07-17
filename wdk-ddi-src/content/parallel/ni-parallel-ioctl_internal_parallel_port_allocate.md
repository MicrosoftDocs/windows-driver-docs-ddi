---
UID: NI:parallel.IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE
title: IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE (parallel.h)
description: The IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE request allocates a parallel port for exclusive access by a client.
old-location: parports\ioctl_internal_parallel_port_allocate.htm
tech.root: parports
ms.assetid: de088a25-c9ad-4d48-b9cb-d0e6958ce164
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE IOCTL"]
ms.keywords: IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE, IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE control code [Parallel Ports], cisspd_79cabd40-4310-48c4-9ee3-f7b50fc60f6f.xml, parallel/IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE, parports.ioctl_internal_parallel_port_allocate
f1_keywords:
 - "parallel/IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE"
 - "IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE"
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
- IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</b> request allocates a parallel port for exclusive access by a client. Before accessing port hardware, a client must first allocate it.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544809(v=vs.85)">Synchronizing the Use of a ParallelPort</a>.


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

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_free.md">IOCTL_INTERNAL_PARALLEL_PORT_FREE</a>



 

 


