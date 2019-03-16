---
UID: NI:parallel.IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE
title: IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE (parallel.h)
description: The IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE request clears the operating mode of a parallel port.
old-location: parports\ioctl_internal_parallel_clear_chip_mode.htm
tech.root: parports
ms.assetid: bca93bca-96f6-46bb-ba24-9f39b5ad1ab4
ms.date: 02/15/2018
ms.keywords: IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE, IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE control code [Parallel Ports], cisspd_912d58fe-f6f8-40c5-b4fe-e8237ea64c04.xml, parallel/IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE, parports.ioctl_internal_parallel_clear_chip_mode
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- parallel.h
api_name:
- IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE</b> request clears the operating mode of a parallel port.

For more information see, <a href="https://msdn.microsoft.com/a22cdeef-4ae7-49f8-b0b5-a4d68feb4235">Setting and Clearing the Communication Mode on a ParallelPort</a>.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\parallel\ns-parallel-_parallel_chip_mode.md">PARALLEL_CHIP_MODE</a> structure that the client allocates to input chip mode information. The client sets the <b>ModeFlags</b> member to the current operating mode.


### -input-buffer-length

The request sets the <b>Parameters.DeviceIoControl.InputBufferLength</b> member to the size, in bytes, of a PARALLEL_CHIP_MODE structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:




#### -STATUS_BUFFER_TOO_SMALL

The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_CHIP_MODE structure.


#### -STATUS_INVALID_DEVICE_STATE

The specified operating mode is not the same as the current operating mode of the parallel port.


## -see-also

<a href="..\parallel\ns-parallel-_parallel_chip_mode.md">PARALLEL_CHIP_MODE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_set_chip_mode.md">IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE</a>



 

 


