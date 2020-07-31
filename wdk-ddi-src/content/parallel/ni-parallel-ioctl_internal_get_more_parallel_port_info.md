---
UID: NI:parallel.IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO
title: IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO (parallel.h)
description: The IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO request returns information about a parallel port.
old-location: parports\ioctl_internal_get_more_parallel_port_info.htm
tech.root: parports
ms.assetid: fe5b9b54-b1b6-48e2-b464-f0f3e9845917
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO IOCTL"]
ms.keywords: IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO, IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO control code [Parallel Ports], cisspd_3f4efeec-5579-44c6-8438-bdb4b4983194.xml, parallel/IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO, parports.ioctl_internal_get_more_parallel_port_info
f1_keywords:
 - "parallel/IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO"
 - "IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO"
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
- IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO</b> request returns information about a parallel port. This information supplements the information that a client obtains by using an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a> request. The additional information about the parallel port includes the type of system interface, the bus number, and the interrupt resources used by the port.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544223(v=vs.85)">Obtaining Information About a ParallelPort</a>.


## -ioctlparameters




### -input-buffer

A <a href="..\parallel\ns-parallel-_more_parallel_port_information.md">MORE_PARALLEL_PORT_INFORMATION</a> structure.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\parallel\ns-parallel-_more_parallel_port_information.md">MORE_PARALLEL_PORT_INFORMATION</a> structure.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a MORE_PARALLEL_PORT_INFORMATION structure that the client allocates to output parallel port information.


### -output-buffer-length

The size of a MORE_PARALLEL_PORT_INFORMATION structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request succeeds, the <b>Information</b> member is set to the size, in bytes, of the MORE_PARALLEL_PORT_INFORMATION structure. Otherwise; the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to the following value:




**STATUS_BUFFER_TOO_SMALL**

The value of the <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is less than the size, in bytes, of a MORE_PARALLEL_PORT_INFORMATION structure.


## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md">IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</a>



<a href="..\parallel\ns-parallel-_more_parallel_port_information.md">MORE_PARALLEL_PORT_INFORMATION</a>



 

 


