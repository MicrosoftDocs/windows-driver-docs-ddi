---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
title: IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY (usbioctl.h)
description: The IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY IOCTL is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_notify_idle_ready.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY IOCTL"]
ms.keywords: IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY, IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY control, IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY control code [Buses], buses.ioctl_internal_usb_notify_idle_ready, usbioctl/IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
req.header: usbioctl.h
req.include-header: 
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
req.typenames: 
f1_keywords:
 - IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
 - usbioctl/IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
---

# IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY IOCTL


## -description

 The <b>IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY</b> IOCTL is used by the USB hub driver. Do not use.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_INTERNAL_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-internal-device-control)

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).
