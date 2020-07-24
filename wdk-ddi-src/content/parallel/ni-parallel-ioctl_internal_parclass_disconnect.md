---
UID: NI:parallel.IOCTL_INTERNAL_PARCLASS_DISCONNECT
title: IOCTL_INTERNAL_PARCLASS_DISCONNECT (parallel.h)
description: The IOCTL_INTERNAL_PARCLASS_DISCONNECT request disconnects a client from a parallel device.
old-location: parports\ioctl_internal_parclass_disconnect.htm
tech.root: parports
ms.assetid: 05dae212-62b8-4cd3-9fd1-495ae56dfada
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_PARCLASS_DISCONNECT IOCTL"]
ms.keywords: IOCTL_INTERNAL_PARCLASS_DISCONNECT, IOCTL_INTERNAL_PARCLASS_DISCONNECT control code [Parallel Ports], cisspd_6459be75-4a0e-4a38-9bc4-b862766951fb.xml, parallel/IOCTL_INTERNAL_PARCLASS_DISCONNECT, parports.ioctl_internal_parclass_disconnect
f1_keywords:
 - "parallel/IOCTL_INTERNAL_PARCLASS_DISCONNECT"
 - "IOCTL_INTERNAL_PARCLASS_DISCONNECT"
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
- IOCTL_INTERNAL_PARCLASS_DISCONNECT
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_PARCLASS_DISCONNECT IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_PARCLASS_DISCONNECT</b> request disconnects a client from a parallel device. After disconnecting from a parallel device, a client must not use any information obtained from a previous <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff543942(v=vs.85)">Connecting to a Parallel Device</a>.


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

<a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a>



 

 


