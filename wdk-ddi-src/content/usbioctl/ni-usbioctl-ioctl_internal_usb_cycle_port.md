---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_CYCLE_PORT
title: IOCTL_INTERNAL_USB_CYCLE_PORT (usbioctl.h)
description: The IOCTL_INTERNAL_USB_CYCLE_PORT I/O request simulates a device unplug and replug on the port associated with the PDO.
old-location: buses\ioctl_internal_usb_cycle_port.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USB_CYCLE_PORT IOCTL"]
ms.keywords: IOCTL_INTERNAL_USB_CYCLE_PORT, IOCTL_INTERNAL_USB_CYCLE_PORT control, IOCTL_INTERNAL_USB_CYCLE_PORT control code [Buses], buses.ioctl_internal_usb_cycle_port, usbioctl/IOCTL_INTERNAL_USB_CYCLE_PORT, usbirp_0f04d439-7813-4da8-9279-a4d113871687.xml
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP and later operating systems.
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
req.typenames: 
f1_keywords:
 - IOCTL_INTERNAL_USB_CYCLE_PORT
 - usbioctl/IOCTL_INTERNAL_USB_CYCLE_PORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - IOCTL_INTERNAL_USB_CYCLE_PORT
---

# IOCTL_INTERNAL_USB_CYCLE_PORT IOCTL


## -description

The <b>IOCTL_INTERNAL_USB_CYCLE_PORT</b> I/O request simulates a device unplug and replug on the port associated with the PDO. 

Drivers should cancel all I/O requests and wait for them to complete before initiating this operation. 

A driver that manages an individual interface on a composite device cannot cycle the port to which the device is attached without affecting the entire composite device and all of its interfaces. For this reason, drivers that manage interfaces should attempt other types of error recovery, such as resetting pipes (<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb_pipe_request">_URB_PIPE_REQUEST</a>), before cycling the port. 

<b>IOCTL_INTERNAL_USB_CYCLE_PORT</b> is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.

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

The bus or port driver sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.
