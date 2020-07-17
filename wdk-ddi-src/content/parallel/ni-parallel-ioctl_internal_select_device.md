---
UID: NI:parallel.IOCTL_INTERNAL_SELECT_DEVICE
title: IOCTL_INTERNAL_SELECT_DEVICE (parallel.h)
description: The IOCTL_INTERNAL_SELECT_DEVICE request:Allocates the parallel portThe system-supplied function driver for parallel ports allocates the parallel port if the client does not set the PAR_HAVE_PORT_KEEP_PORT flag in the CommandFlags member of the input PARALLEL_1284_COMMAND structure. Otherwise, the parallel port function driver does not allocate the parallel port.Selects an IEEE 1284.3 daisy chain parallel device or an end-of-chain device attached to the parallel portAlthough a client can select an end-of-chain device using a select device request, Microsoft recommends using an IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE request instead. The parallel port function driver selects the end-of-chain device before it allocates the parallel port to a client.
old-location: parports\ioctl_internal_select_device.htm
tech.root: parports
ms.assetid: d072a97d-f15d-44e9-b7d5-4fb872bfcbf0
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_SELECT_DEVICE IOCTL"]
ms.keywords: IOCTL_INTERNAL_SELECT_DEVICE, IOCTL_INTERNAL_SELECT_DEVICE control code [Parallel Ports], cisspd_e884bf73-c8d2-4007-a01a-ba6af4fd8359.xml, parallel/IOCTL_INTERNAL_SELECT_DEVICE, parports.ioctl_internal_select_device
f1_keywords:
 - "parallel/IOCTL_INTERNAL_SELECT_DEVICE"
 - "IOCTL_INTERNAL_SELECT_DEVICE"
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
- IOCTL_INTERNAL_SELECT_DEVICE
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_SELECT_DEVICE IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The <b>IOCTL_INTERNAL_SELECT_DEVICE</b> request:

<ul>
<li>
Allocates the parallel port

The system-supplied function driver for parallel ports allocates the parallel port if the client does not set the PAR_HAVE_PORT_KEEP_PORT flag in the <b>CommandFlags</b> member of the input PARALLEL_1284_COMMAND structure. Otherwise, the parallel port function driver does not allocate the parallel port.

</li>
<li>
Selects an IEEE 1284.3 daisy chain parallel device or an end-of-chain device attached to the parallel port

Although a client can select an end-of-chain device using a select device request, Microsoft recommends using an <a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a> request instead. The parallel port function driver selects the end-of-chain device before it allocates the parallel port to a client.

</li>
</ul>


For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544793(v=vs.85)">Selecting and Deselecting an IEEE 1284 Device Attached to a ParallelPort</a>.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> points to a <a href="..\parallel\ns-parallel-_parallel_1284_command.md">PARALLEL_1284_COMMAND</a> structure that the client allocates to input the select device information.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member specifies the size, in bytes, of a PARALLEL_1284_COMMAND structure.


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

The specified device is not flagged internally as an end-of-chain device and the value of the <b>ID</b> member of the input structure is greater than the number of existing daisy chain devices.


## -see-also

<a href="..\parallel\ns-parallel-_parallel_1284_command.md">PARALLEL_1284_COMMAND</a>



<a href="..\parallel\ni-parallel-ioctl_internal_deselect_device.md">IOCTL_INTERNAL_DESELECT_DEVICE</a>



 

 


