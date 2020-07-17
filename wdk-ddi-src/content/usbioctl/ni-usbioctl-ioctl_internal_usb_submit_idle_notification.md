---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION
title: IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION (usbioctl.h)
description: The IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION I/O request is used by drivers to inform the USB bus driver that a device is idle and can be suspended.
old-location: buses\ioctl_internal_usb_submit_idle_notification.htm
tech.root: usbref
ms.assetid: e7ce1448-223f-4aea-b5e7-70a3b2f58e77
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION IOCTL"]
ms.keywords: IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION, IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION control, IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION control code [Buses], buses.ioctl_internal_usb_submit_idle_notification, usbioctl/IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION, usbirp_4a27792b-b726-4741-9d59-5e2b70a3b1c6.xml
f1_keywords:
 - "usbioctl/IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION"
 - "IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION"
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
- Usbioctl.h
api_name:
- IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION IOCTL

## -description

The **IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION** I/O request is used by drivers to inform the USB bus driver that a device is idle and can be suspended.

When sending this IOCTL, caller must furnish a callback routine that does the actual suspension of the device. The USB bus driver will call this routine at PASSIVE_LEVEL when it is safe for the device to be powered down. If the device supports remote wake up and has no Wait/Wake IRP already pending, the callback routine should submit a Wait/Wake IRP to the bus driver for the device, before powering it down. 

For additional information, see [Supporting Devices that Have Wake-Up Capabilities](https://docs.microsoft.com/windows-hardware/drivers/kernel/supporting-devices-that-have-wake-up-capabilities)

**IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION** is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.

## -ioctlparameters

### -input-buffer

**Parameters.DeviceIoControl.Type3InputBuffer** should be a pointer to a **USB_IDLE_CALLBACK_INFO** structure. This structure should contain a pointer to the callback routine and a pointer to the callback routine context. 

The structure holding the callback information is defined in usbioctl.h as follows:

```c++
typedef VOID (*USB_IDLE_CALLBACK)(PVOID Context);

typedef struct _USB_IDLE_CALLBACK_INFO
{
  USB_IDLE_CALLBACK IdleCallback;
  PVOID IdleContext;
} USB_IDLE_CALLBACK_INFO, *PUSB_IDLE_CALLBACK_INFO;
```

### -input-buffer-length

The size of a **USB_IDLE_CALLBACK_INFO** structure.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The bus or port driver sets **Irp->IoStatus.Status** to STATUS_SUCCESS or the appropriate error status.
