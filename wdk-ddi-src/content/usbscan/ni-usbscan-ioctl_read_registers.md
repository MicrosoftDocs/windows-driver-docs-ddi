---
UID: NI:usbscan.IOCTL_READ_REGISTERS
title: IOCTL_READ_REGISTERS (usbscan.h)
description: Reads from USB device registers, using the control pipe.
tech.root: image
ms.date: 03/08/2023
keywords: ["IOCTL_READ_REGISTERS IOCTL"]
ms.keywords: IOCTL_READ_REGISTERS, IOCTL_READ_REGISTERS control, IOCTL_READ_REGISTERS control code [Imaging Devices], image.ioctl_read_registers, stifnc_68af86d1-7d3b-4d2c-a5af-983f0339d71f.xml, usbscan/IOCTL_READ_REGISTERS
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_READ_REGISTERS
 - usbscan/IOCTL_READ_REGISTERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbscan.h
api_name:
 - IOCTL_READ_REGISTERS
---

## -description

Reads from USB device registers, using the control pipe.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

Pointer to an [IO_BLOCK](./ns-usbscan-_io_block.md) structure.

### -input-buffer-length

Size of the input buffer.

### -output-buffer

Pointer to a buffer to receive register contents.

### -output-buffer-length

Size of the output buffer. The value must match the contents of the **uLength** member of the IO_BLOCK structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -remarks

### DeviceIoControl Parameters

When the **DeviceloControl** function is called with the IOCTL_READ_REGISTERS I/O control code, the caller must specify the address of an [IO_BLOCK](./ns-usbscan-_io_block.md) structure as the function's *lpInBuffer* parameter.

Using the IO_BLOCK contents, the kernel-mode driver creates a [URB](../usb/ns-usb-_urb.md) that contains a [_URB_CONTROL_VENDOR_OR_CLASS_REQUEST](../usb/ns-usb-_urb_control_vendor_or_class_request.md) structure.

The following table indicates the values assigned to _URB_CONTROL_VENDOR_OR_CLASS_REQUEST structure members.

| Structure Member | Value Assigned |
|---|---|
| **TransferFlags** | 1 |
| **TransferBufferLength** | *pIoBlock*-\>**uLength** |
| **TransferBuffer** | [DeviceIoControl](/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol)'s *lpOutBuffer* argument. |
| **TransferBufferMDL** | **NULL** |
| **RequestTypeReservedBits** | 0xC0 |
| **Request** | (*pIoBlock*-\>**uLength** \> 1) ? 0x04 : 0x0C |
| **Value** | (**SHORT**)*pIoBlock*-\>**uOffset** |
| **Index** | *pIoBlock*-\>**uIndex** |

For more information, see [Accessing Kernel-Mode Drivers for Still Image Devices](/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices).