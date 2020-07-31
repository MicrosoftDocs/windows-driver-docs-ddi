---
UID: NI:parallel.IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO
title: IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO (parallel.h)
description: The IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO request returns STATUS_SUCCESS.
old-location: parports\ioctl_internal_release_parallel_port_info.htm
tech.root: parports
ms.assetid: 1a28e6db-b140-42aa-be52-fb5655983383
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO IOCTL"]
ms.keywords: IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO, IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO control code [Parallel Ports], cisspd_3bbcd68f-ea0d-46c8-8aab-0e33dcb4afad.xml, parallel/IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO, parports.ioctl_internal_release_parallel_port_info
f1_keywords:
 - "parallel/IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO"
 - "IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO"
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
- IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO</b> request returns STATUS_SUCCESS.
<div class="alert"><b>Note</b>    The intended purpose of this IOCTL is to make it possible to page the callback routines supported by the system-supplied function driver for parallel ports. However, this capability is not yet implemented.</div><div> </div>

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

<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_more_parallel_port_info.md">IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md">IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</a>



 

 


