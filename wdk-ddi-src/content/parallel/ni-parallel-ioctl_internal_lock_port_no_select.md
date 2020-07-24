---
UID: NI:parallel.IOCTL_INTERNAL_LOCK_PORT_NO_SELECT
title: IOCTL_INTERNAL_LOCK_PORT_NO_SELECT (parallel.h)
description: The IOCTL_INTERNAL_LOCK_PORT_NO_SELECT request allocates the parallel device's parent parallel port, but does not select the parallel device.
old-location: parports\ioctl_internal_lock_port_no_select.htm
tech.root: parports
ms.assetid: 4ff7fb02-707f-49a3-a1eb-dcf3353f2803
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_LOCK_PORT_NO_SELECT IOCTL"]
ms.keywords: IOCTL_INTERNAL_LOCK_PORT_NO_SELECT, IOCTL_INTERNAL_LOCK_PORT_NO_SELECT control code [Parallel Ports], cisspd_a8b5a024-9169-47ef-843d-706a0322247b.xml, parallel/IOCTL_INTERNAL_LOCK_PORT_NO_SELECT, parports.ioctl_internal_lock_port_no_select
f1_keywords:
 - "parallel/IOCTL_INTERNAL_LOCK_PORT_NO_SELECT"
 - "IOCTL_INTERNAL_LOCK_PORT_NO_SELECT"
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
- IOCTL_INTERNAL_LOCK_PORT_NO_SELECT
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_LOCK_PORT_NO_SELECT IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_LOCK_PORT_NO_SELECT</b> request allocates the parallel device's parent parallel port, but does not select the parallel device.

This request is only supported in Windows XP and later.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544195(v=vs.85)">Locking and Unlocking a ParallelPort for Use by a Parallel Device</a>.


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

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices.


## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_unlock_port_no_deselect.md">IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_unlock_port.md">IOCTL_INTERNAL_UNLOCK_PORT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a>



 

 


