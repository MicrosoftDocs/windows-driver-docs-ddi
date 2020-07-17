---
UID: NI:parallel.IOCTL_INTERNAL_DESELECT_DEVICE
title: IOCTL_INTERNAL_DESELECT_DEVICE (parallel.h)
description: The IOCTL_INTERNAL_DESELECT_DEVICE request deselects an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device attached to a parallel port.
old-location: parports\ioctl_internal_deselect_device.htm
tech.root: parports
ms.assetid: 39cb818e-6219-4d7e-8114-8c0dfdfff76e
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_DESELECT_DEVICE IOCTL"]
ms.keywords: IOCTL_INTERNAL_DESELECT_DEVICE, IOCTL_INTERNAL_DESELECT_DEVICE control code [Parallel Ports], cisspd_8ade9861-f2cd-4328-9f8a-92fa4b2d2163.xml, parallel/IOCTL_INTERNAL_DESELECT_DEVICE, parports.ioctl_internal_deselect_device
f1_keywords:
 - "parallel/IOCTL_INTERNAL_DESELECT_DEVICE"
 - "IOCTL_INTERNAL_DESELECT_DEVICE"
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
- IOCTL_INTERNAL_DESELECT_DEVICE
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_DESELECT_DEVICE IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_DESELECT_DEVICE</b> request deselects an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device attached to a parallel port.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544793(v=vs.85)">Selecting and Deselecting an IEEE 1284 Device Attached to a ParallelPort</a>.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\parallel\ns-parallel-_parallel_1284_command.md">PARALLEL_1284_COMMAND</a> structure that the client allocates to input IEEE 1284.3 command information. The client can free the parallel port by not setting the PAR_HAVE_PORT_KEEP_PORT flag in the <b>CommandFlags</b> member.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member specifies the size, in bytes, of the PARALLEL_1284_COMMAND structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:




**STATUS_BUFFER_TOO_SMALL**

The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_1284_COMMAND structure.


**STATUS_INVALID_PARAMETER**

The specified device is not flagged internally as an end-of-chain device, and the specified ID value is greater than the number of existing daisy-chain devices.


## -see-also

<a href="..\parallel\ns-parallel-_parallel_1284_command.md">PARALLEL_1284_COMMAND</a>



<a href="..\parallel\ni-parallel-ioctl_internal_select_device.md">IOCTL_INTERNAL_SELECT_DEVICE</a>



 

 


