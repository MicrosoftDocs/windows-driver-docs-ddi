---
UID: NI:parallel.IOCTL_INTERNAL_UNLOCK_PORT
title: IOCTL_INTERNAL_UNLOCK_PORT (parallel.h)
description: The IOCTL_INTERNAL_UNLOCK_PORT request deselects a parallel device and frees the parallel device's parent parallel port.
old-location: parports\ioctl_internal_unlock_port.htm
tech.root: parports
ms.assetid: cc895a21-16bb-4a49-980c-8c6023d6aed4
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_UNLOCK_PORT IOCTL"]
ms.keywords: IOCTL_INTERNAL_UNLOCK_PORT, IOCTL_INTERNAL_UNLOCK_PORT control code [Parallel Ports], cisspd_2f7b8b18-f3cb-41e4-bdb7-4475f3b8655f.xml, parallel/IOCTL_INTERNAL_UNLOCK_PORT, parports.ioctl_internal_unlock_port
f1_keywords:
 - "parallel/IOCTL_INTERNAL_UNLOCK_PORT"
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
- IOCTL_INTERNAL_UNLOCK_PORT
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_UNLOCK_PORT IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_UNLOCK_PORT</b> request deselects a parallel device and frees the parallel device's parent parallel port.

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



<a href="..\parallel\ni-parallel-ioctl_internal_lock_port_no_select.md">IOCTL_INTERNAL_LOCK_PORT_NO_SELECT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a>



 

 


