---
UID: NI:parallel.IOCTL_INTERNAL_PARCLASS_CONNECT
title: IOCTL_INTERNAL_PARCLASS_CONNECT (parallel.h)
description: The IOCTL_INTERNAL_PARCLASS_CONNECT request returns information about a parallel port and the callback routines that the system-supplied bus driver for parallel ports provides to operate the parallel port.
old-location: parports\ioctl_internal_parclass_connect.htm
tech.root: parports
ms.assetid: 77dc31a1-a50c-4727-b730-1785e5d4a355
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_PARCLASS_CONNECT IOCTL"]
ms.keywords: IOCTL_INTERNAL_PARCLASS_CONNECT, IOCTL_INTERNAL_PARCLASS_CONNECT control code [Parallel Ports], cisspd_03b94b78-be74-4421-bb08-0860d6d8dca5.xml, parallel/IOCTL_INTERNAL_PARCLASS_CONNECT, parports.ioctl_internal_parclass_connect
f1_keywords:
 - "parallel/IOCTL_INTERNAL_PARCLASS_CONNECT"
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
- IOCTL_INTERNAL_PARCLASS_CONNECT
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_PARCLASS_CONNECT IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_PARCLASS_CONNECT</b> request returns information about a parallel port and the callback routines that the system-supplied bus driver for parallel ports provides to operate the parallel port.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff543942(v=vs.85)">Connecting to a Parallel Device</a>.


## -ioctlparameters




### -input-buffer

A <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure.


### -input-buffer-length

The value of the <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure that the client allocates to output information.


### -output-buffer-length

The size of a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a PARCLASS_INFORMATION structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices or to the following value:




#### -STATUS_BUFFER_TOO_SMALL

The value of the <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is less than the size, in bytes, of a PARCLASS_INFORMATION structure.


## -see-also

<a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parclass_disconnect.md">IOCTL_INTERNAL_PARCLASS_DISCONNECT</a>



 

 


