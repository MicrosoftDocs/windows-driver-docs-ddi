---
UID: NI:parallel.IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO
title: IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO
author: windows-driver-content
description: The IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO request returns Plug and Play information about a parallel port.
old-location: parports\ioctl_internal_get_parallel_pnp_info.htm
tech.root: parports
ms.assetid: 9a93d91a-e9b8-41f5-8d15-f693336bee07
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO, IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO control code [Parallel Ports], cisspd_66e27d46-1bd9-4e14-8b3f-4d7760552498.xml, parallel/IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO, parports.ioctl_internal_get_parallel_pnp_info
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</b> request returns Plug and Play information about a parallel port.

For more information, see <a href="https://msdn.microsoft.com/d8ae2296-05b6-419a-93cc-00fcb12d41fe">Obtaining Information About a ParallelPort</a>.


## -ioctlparameters




### -input-buffer

A <a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a> structure.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a> structure.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a PARALLEL_PNP_INFORMATION structure that the client allocates to output Plug and Play information.


### -output-buffer-length

The size of a PARALLEL_PNP_INFORMATION structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to the following value:




#### -STATUS_BUFFER_TOO_SMALL

The value of <b>Parameters.DeviceIoControl.OutputBufferLength</b> is less than the size, in bytes, of a PARALLEL_PNP_INFORMATION structure.


## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_more_parallel_port_info.md">IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a>



 

 


