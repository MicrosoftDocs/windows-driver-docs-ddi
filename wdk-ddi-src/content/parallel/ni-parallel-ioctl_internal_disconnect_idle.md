---
UID: NI:parallel.IOCTL_INTERNAL_DISCONNECT_IDLE
title: IOCTL_INTERNAL_DISCONNECT_IDLE (parallel.h)
description: The IOCTL_INTERNAL_DISCONNECT_IDLE request disconnects the IEEE 1284 operating modes that are set for a parallel device.
old-location: parports\ioctl_internal_disconnect_idle.htm
tech.root: parports
ms.assetid: 02fd4277-502d-4a9e-b809-10134ed0900b
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_DISCONNECT_IDLE IOCTL"]
ms.keywords: IOCTL_INTERNAL_DISCONNECT_IDLE, IOCTL_INTERNAL_DISCONNECT_IDLE control code [Parallel Ports], cisspd_ff4b2feb-d3b4-4b80-9f6f-f4fd16bab4c1.xml, parallel/IOCTL_INTERNAL_DISCONNECT_IDLE, parports.ioctl_internal_disconnect_idle
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
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
f1_keywords:
 - IOCTL_INTERNAL_DISCONNECT_IDLE
 - parallel/IOCTL_INTERNAL_DISCONNECT_IDLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - parallel.h
api_name:
 - IOCTL_INTERNAL_DISCONNECT_IDLE
---

# IOCTL_INTERNAL_DISCONNECT_IDLE IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

The <b>IOCTL_INTERNAL_DISCONNECT_IDLE</b> request disconnects the IEEE 1284 operating modes that are set for a parallel device. The system-supplied bus driver for parallel ports sets the default operating mode to IEEE 1284-compatible.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544797(v=vs.85)">Setting and Clearing a Communication Mode for a Parallel Device</a>.

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

<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_device_caps.md">IOCTL_PAR_GET_DEVICE_CAPS</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>

