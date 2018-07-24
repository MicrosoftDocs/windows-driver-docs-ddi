---
UID: NI:parallel.IOCTL_INTERNAL_LOCK_PORT
title: IOCTL_INTERNAL_LOCK_PORT
author: windows-driver-content
description: The IOCTL_INTERNAL_LOCK_PORT request allocates the parallel device's parent parallel port and selects the parallel device on the port.
old-location: parports\ioctl_internal_lock_port.htm
tech.root: parports
ms.assetid: 561816b1-f9e7-49c9-b655-583adf293926
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_LOCK_PORT, IOCTL_INTERNAL_LOCK_PORT control code [Parallel Ports], cisspd_2338a5ae-b61e-44c6-8ddd-3666f5fb24ee.xml, parallel/IOCTL_INTERNAL_LOCK_PORT, parports.ioctl_internal_lock_port
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
-	IOCTL_INTERNAL_LOCK_PORT
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_LOCK_PORT IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_LOCK_PORT</b> request allocates the parallel device's parent parallel port and selects the parallel device on the port.

For more information, see <a href="https://msdn.microsoft.com/dbfa962e-9de8-4a9c-b962-24b53c41f35d">Locking and Unlocking a ParallelPort for Use by a Parallel Device</a>.


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

<a href="..\parallel\ni-parallel-ioctl_internal_unlock_port.md">IOCTL_INTERNAL_UNLOCK_PORT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_unlock_port_no_deselect.md">IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_lock_port_no_select.md">IOCTL_INTERNAL_LOCK_PORT_NO_SELECT</a>



 

 


