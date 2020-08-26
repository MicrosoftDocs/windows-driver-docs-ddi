---
UID: NI:usbscan.IOCTL_SET_TIMEOUT
title: IOCTL_SET_TIMEOUT (usbscan.h)
description: Sets the time-out value for USB bulk IN, bulk OUT, or interrupt pipe access.
old-location: image\ioctl_set_timeout.htm
tech.root: image
ms.assetid: 90403ef3-d86c-4e2b-842d-c121cce07a47
ms.date: 05/03/2018
keywords: ["IOCTL_SET_TIMEOUT IOCTL"]
ms.keywords: IOCTL_SET_TIMEOUT, IOCTL_SET_TIMEOUT control, IOCTL_SET_TIMEOUT control code [Imaging Devices], image.ioctl_set_timeout, stifnc_942a0b21-7e68-444d-8bf2-7f8388a8a8fc.xml, usbscan/IOCTL_SET_TIMEOUT
f1_keywords:
 - "usbscan/IOCTL_SET_TIMEOUT"
 - "IOCTL_SET_TIMEOUT"
req.header: usbscan.h
req.include-header: Usbscan.h
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
- Usbscan.h
api_name:
- IOCTL_SET_TIMEOUT
targetos: Windows
req.typenames: 
---

# IOCTL_SET_TIMEOUT IOCTL

## -description

Sets the time-out value for USB bulk IN, bulk OUT, or interrupt pipe access.

## -ioctlparameters

### -input-buffer

Pointer to a [USBSCAN_TIMEOUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_usbscan_timeout) structure.

### -input-buffer-length

Size of the input buffer.

### -output-buffer

**NULL**.

### -output-buffer-length

Zero.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -remarks

### DeviceIoControl Parameters</h3>

When the **DeviceloControl** function is called with the IOCTL_SET_TIMEOUT I/O control code, the caller must specify the address of a [USBSCAN_TIMEOUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_usbscan_timeout) structure as the function's *lpInBuffer* parameter.

Using the USBSCAN_TIMEOUT structure's contents, the kernel-mode driver resets the time-out value for each type of operation: bulk IN read, bulk OUT write, or interrupt.

For more information, see [Accessing Kernel-Mode Drivers for Still Image Devices](https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices).

> [!NOTE]
> The default time-out value is 120 seconds. The maximum time-out value is 214 seconds. Values greater than 214 seconds will cause transfer time-outs.
